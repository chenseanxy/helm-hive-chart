  
FROM chenseanxy/hadoop:3.2.1-nolib

ARG VERSION=

ADD apache-hive-${VERSION}-bin.tar.gz /opt

RUN cd /opt && ln -s ./apache-hive-${VERSION}-bin hive

ADD mysql-connector-java-8.0.18.jar /opt/hive/lib

WORKDIR /opt/hive
