FROM java:8-jre-alpine
MAINTAINER New Relic <support@newrelic.com>

ENV PLUGIN_VERSION=newrelic_mysql_plugin-2.0.0

ADD https://github.com/newrelic-platform/newrelic_mysql_java_plugin/raw/master/dist/${PLUGIN_VERSION}.tar.gz /tmp/
RUN mkdir -p /usr/src/myapp/ && tar -C /usr/src/myapp/ -xzf /tmp/${PLUGIN_VERSION}.tar.gz

ADD configure-and-run required-variables.list /usr/src/myapp/${PLUGIN_VERSION}/
WORKDIR /usr/src/myapp/${PLUGIN_VERSION}

ENV NEW_RELIC_LICENSE_KEY="" NEW_RELIC_LOG_LEVEL="info"
ENV PLUGIN_NAME="" PLUGIN_HOST="" PLUGIN_METRICS="status,newrelic" PLUGIN_USER="" PLUGIN_PASSWD=""

CMD ["./configure-and-run"]
