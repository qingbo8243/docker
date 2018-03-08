# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          centos:7.1.1503
MAINTAINER   qingbo.liu<260831882@qq.com>

ADD  ./jdk-7u80-linux-x64.tar.gz /home/jdk/
ADD  ./jdk-8u151-linux-x64.tar.gz /home/jdk/
ADD  ./apache-maven-3.3.3-bin.tar.gz /home/maven/
ADD  ./apache-tomcat-7.0.55.tar.gz /home/tomcat/

ENV JAVA_VERSION 1.7.0_80
#ENV JAVA_HOME /home/jdk/jdk1.7.0_80
ENV JAVA_HOME /home/jdk/jdk1.8.0_151


ENV MAVEN_VERSION 3.3.3
ENV M2_HOME /home/maven/apache-maven-3.3.3

ENV TOMCAT_VERSION 7.0.55
ENV CATALINA_HOME /home/tomcat/apache-tomcat-7.0.55
ENV CATALINA_BASE /home/tomcat/apache-tomcat-7.0.55

ENV CLASSPATH $JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin:$CATALINA_HOME/lib:$CATALINA_HOME/bin:$M2_HOME/bin
ENV APP_DIR ${CATALINA_HOME}/webapps/

COPY ./server.xml /home/tomcat/apache-tomcat-7.0.55/conf/server.xml
COPY ./settings.xml /home/maven/apache-maven-3.3.3/conf/settings.xml
COPY ./jenkins.war /home/tomcat/apache-tomcat-7.0.55/webapps/

RUN yum install -y libtool-ltdl git

EXPOSE 8080

ENTRYPOINT /home/tomcat/apache-tomcat-7.0.55/bin/catalina.sh run