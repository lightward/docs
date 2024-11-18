# SSH

A [rough edge](rough-edges.md): `fly ssh console` doesn't support addressing a specific Machine.

## Connecting to a random Machine

```sh
$ fly ssh console -a $FLY_APP_NAME
$ $ bin/rails c
```

## Connecting to a specific Machine

This will display an interactive list of Machines to choose from. Good for small numbers of Machines, not great for large ones.

```sh
$ fly ssh console -a $FLY_APP_NAME -s
```

## Connecting to a specific Machine address for a given app

When an app has hundreds of Machines, it's faster on average to just look up the IP address of the desired Machine and pass that back to `fly ssh console`.

```sh
# get the Machine's IPv6 address
$ fly m status $MACHINE_ID

# use that address here
$ fly ssh console -a $FLY_APP_NAME -A $IP_ADDRESS
```
