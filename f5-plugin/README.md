# The New Relic F5 Plugin

This is the New Relic Plugin for monitoring F5 Load Balancers. It is the same one that can be found in Plugin Central.

# How to use this image

In order to function, the plugin needs a few environment variables set:

* `NEW_RELIC_LICENSE_KEY`
* `PLUGIN_HOSTNAME`

Optionally, you can also set:

* `NEW_RELIC_LOG_LEVEL`
* `PLUGIN_PORT`
* `PLUGIN_SNMP_COMMUNITY`

## Example

```shell
$ docker run -d \
  -e NEW_RELIC_LICENSE_KEY=foobarbaz \
  -e PLUGIN_HOSTNAME=my-real-big-lb-host \
  -e PLUGIN_SNMP_COMMUNITY=coolcommunity \
  newrelic/f5-plugin
```
