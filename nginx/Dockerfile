FROM nginx:1.11.0
MAINTAINER Petyo Dimitrov
ENV REFRESHED_AT 2016-05-24

ENV NEXUS_HOST nexus
ENV NEXUS_PORT 8081
ENV NEXUS_ARTIFACT http://${NEXUS_HOST}:${NEXUS_PORT}/service/local/artifact/maven/redirect?r=snapshots&g=org.cloudfoundry.samples&a=spring-music&v=1.0-SNAPSHOT&p=zip&c=static
ENV ZIP_FILE spring-music-static.zip

RUN apt-get update -y && \
  apt-get install wget unzip -y && \
  wget -O /tmp/${ZIP_FILE} ${NEXUS_ARTIFACT} && \
  unzip /tmp/${ZIP_FILE} -d /usr/share/nginx/assets/

COPY default.conf /etc/nginx/conf.d/default.conf