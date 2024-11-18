# Counting all org machines

{% code overflow="wrap" %}
```
fly apps list --json | jq -r '.[].ID' | xargs -n 1 fly m list -q -a | awk NF | wc -l
```
{% endcode %}
