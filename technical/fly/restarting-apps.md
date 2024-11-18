# Restarting apps

## Not-particularly-recommended path

The normal route for this is `fly apps restart $APP_NAME`.

This works, but (as of this writing) it restarts Fly machines in serial -- and the restart sequence halts if any machine fails to restart normally. (This stuff is documented in [Rough edges](rough-edges.md).)

## Recommended path

This command generates restart commands. If you copy and execute its output, you'll restart all of an app's Fly machines individually and in parallel. **Watch for failures -- it's on you to address them.**

```
fly m list -q -a $APP_NAME | awk NF | awk '{ print "fly m restart " $1 " &;" }'
```

Or, because Isaac just found out about [pbcopy](https://ss64.com/mac/pbcopy.html):

```
 fly m list -q -a $APP_NAME | awk NF | awk '{ print "fly m restart " $1 " &;" }' | pbcopy
```