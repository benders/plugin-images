# The New Relic MySQL Plugin

This is the New Relic Plugin for monitoring MySQL databases. It is the same one that can be found in Plugin Central at [https://rpm.newrelic.com/accounts/1/plugins/directory/52](https://rpm.newrelic.com/accounts/1/plugins/directory/52)

# How to use this image

In order to function, the plugin needs a few environment variables set:

* `NEW_RELIC_LICENSE_KEY`
* `PLUGIN_NAME`
* `PLUGIN_HOST`
* `PLUGIN_USER`
* `PLUGIN_PASSWD`

Optionally, you can also set:

* `NEW_RELIC_LOG_LEVEL`
* `PLUGIN_METRICS` (see [metric.category.json](https://github.com/newrelic-platform/newrelic_mysql_java_plugin/blob/master/config/metric.category.json) for details)

## Example

```shell
$ docker run -d \
  -e NEW_RELIC_LICENSE_KEY=foobarbaz \
  -e PLUGIN_HOST=your-db-host \
  -e PLUGIN_USER=newrelic \
  -e PLUGIN_PASSWD=SuPeRsEcUrE \
  newrelic/mysql-plugin
```
