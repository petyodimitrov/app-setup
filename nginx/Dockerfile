FROM nginx:1.9.5
MAINTAINER Petyo Dimitrov
ENV REFRESHED_AT 2015-10-24

ENV NEXUS_ARTIFACT http://cisetup_nexus_1:8081/service/local/artifact/maven/redirect?r=snapshots&g=org.cloudfoundry.samples&a=spring-music&v=1.0-SNAPSHOT&p=zip&c=static
ENV ZIP_FILE spring-music-static.zip

RUN apt-get update -y && \
  apt-get install wget unzip nano -y && \
  wget -O /tmp/${ZIP_FILE} ${NEXUS_ARTIFACT} && \
  unzip /tmp/${ZIP_FILE} -d /usr/share/nginx/assets/

COPY default.conf /etc/nginx/conf.d/default.conf