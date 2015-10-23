FROM tomcat:8.0
MAINTAINER Petyo Dimitrov
ENV REFRESHED_AT 2015-10-24

ENV NEXUS_ARTIFACT http://cisetup_nexus_1:8081/service/local/artifact/maven/redirect?r=snapshots&g=org.cloudfoundry.samples&a=spring-music&v=1.0-SNAPSHOT&p=war

RUN apt-get update -y && \
  apt-get install wget -y && \
  wget -O /usr/local/tomcat/webapps/ROOT.war ${NEXUS_ARTIFACT} && \
  mv /usr/local/tomcat/webapps/ROOT /usr/local/tomcat/webapps/_ROOT

COPY tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml