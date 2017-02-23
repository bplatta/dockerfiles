# This is largely identical to @stepanstipl's:
#
# https://github.com/stepanstipl/docker-flyway

FROM openjdk:8-jre-alpine

ENV FLYWAY_VERSION 4.1.1
ENV FLYWAY_SQL_DIR /sql

RUN apk update \
  && apk add openssl \
  && mkdir /opt \
  && wget -qO- https://repo1.maven.org/maven2/org/flywaydb/flyway-commandline/4.1.1/flyway-commandline-4.1.1.tar.gz | tar -xzf- -C /opt \
  && mv /opt/flyway-${FLYWAY_VERSION} /opt/flyway \
  && sed -i 's/bash/sh/' /opt/flyway/flyway \
  && echo "flyway.locations=filesystem:${FLYWAY_SQL_DIR}" > /opt/flyway/conf/flyway.conf \
  && echo "flyway.encoding=UTF-8" >> /opt/flyway/conf/flyway.conf

# Default location for sql migrations
VOLUME /sql

ENTRYPOINT ["/opt/flyway/flyway"]

CMD ["-help"]