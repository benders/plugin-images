FROM ruby:2.1
MAINTAINER New Relic <support@newrelic.com>

ENV PLUGIN_VERSION=newrelic_f5_plugin-1.0.18

ADD https://github.com/newrelic-platform/newrelic_f5_plugin/archive/v1.0.18.tar.gz /tmp/
RUN mkdir -p /data/app && tar -C /data/app -xzf /tmp/v1.0.18.tar.gz

ADD write-configs required-variables.txt /data/app/${PLUGIN_VERSION}/
WORKDIR /data/app/${PLUGIN_VERSION}

# RUN bundle config --global frozen 1
RUN bundle install

ENV NEW_RELIC_LICENSE_KEY="" NEW_RELIC_LOG_LEVEL="debug"
ENV PLUGIN_HOSTNAME="" PLUGIN_PORT="161" PLUGIN_SNMP_COMMUNITY="public"

CMD ./write-configs && ./bin/f5_monitor run
