# Recovering from deploy failures

{% hint style="info" %}
In this section, "retry" means "use GitHub Action's retry button on the failed run".
{% endhint %}

## Build failures

You _might_ need to destroy the Fly builder app. It'll get auto-created again when you retry, which is what you should do after destroying the builder app.

## Docker failures

Just retry. It's fine. :)

## Release command failures

Just retry. It's fine. :)

## Machine update failures

Start by surveying the scene, to see how many machines are on the new image vs the old one, or in `replacing` vs `failed` vs `created` status.

```
$ fly m list -a $FLY_APP_NAME
```

### Total machine update failure, i.e. the release command succeeded but no Machines were updated at all

If you're here, the app is probably online but no longer processing background jobs (because all the Sidekiq processes were instructed to enter quiet mode during [the release command](./#release-commands)).

Handle this by rebooting one of the worker\_autoscale machines. That should be enough to start bringing machines back online.

```
$ fly m list -a $FLY_APP_NAME | grep worker_autoscale
$ fly m restart MACHINE_ID
```

Once you've verified that the app is doing work again, wait for it to catch up on the run backlog, and then retry the deploy.

### **A minority of machines were successfully updated**

Manually redo the deploy.

Do this using a [CLI deploy](./#cli-deploys), using the Docker image URI from the build step.

### A majority of machines were successfully updated

Manually update the rest of the machines.

Start by examining `fly m list -a $FLY_APP_NAME`, and build a list of machine IDs that are stuck on the old image.

For each one, do something like this:

```sh
fly m update 328756e9f52758 \
  --env RELEASE_LABEL=v62-3-ga38cb23a \
  --image registry.fly.io/$FLY_APP_NAME:locksmith-api.v62-3-ga38cb23a
```

### Sometimes a machine will get stuck and you'll need to outright destroy it

`fly m destroy MACHINE_ID`

Add `--force` if the machine is stubborn and won’t stop.

and then use `fly scale count` to scale back up to the desired machine count. Search fly scale count in the internal slack and you'll see example usage.
