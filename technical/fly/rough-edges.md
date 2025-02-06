---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Rough edges

Fly is fantastic. Super happy to be on it.

These are the rough edges we've bumped up against, and (when applicable) how we handle it.

## Fly Proxy

* [auto-stop](https://fly.io/docs/apps/autostart-stop) doesn't seeeeeem to work properly when websockets are in the mix

## flyctl

### apps

* restart
  * doesn't support `--process-group`
    * workaround (including backgrounding each Machine's individual restart command):
      * `fly m list -a $APP | grep $PROCESS_GROUP | awk NF | awk '{ print "fly m restart " $1 " &;" }'`
  * slow for restarting large numbers of Machines, and halts if any individual restart fails
    * workaround: use `fly m restart $ID &` instead
    * addressed in [Restarting apps](restarting-apps.md)

### machines

* status
  * no machine-readable output; we regex our way through it to get Machine status
    * nb: `--display-config` exists, but that's for something else
  * doesn't include healthchecks
    * `fly checks list -a $app | grep $machine_id`

### scale

* count
  * it seems to grab a lease on _all_ Machines at once, even when scoped by `--process-group`, which means `fly scale count` commands can't be run concurrently
    * no workaround
