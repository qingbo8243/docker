# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          tomcat:7
MAINTAINER   qingbo.liu<260831882@qq.com>

ADD  ./apache-maven-3.3.3-bin.tar.gz /home/maven/

COPY settings.xml /home/maven/apache-maven-3.3.3/conf/settings.xml
COPY ./jenkins.war $APP_DIR

ENV MAVEN_VERSION 3.3.3
ENV M2_HOME /home/maven/apache-maven-3.3.3
ENV JAVA_HOME /home/jdk/jdk1.8.0_151
ENV PATH $PATH:$JAVA_HOME/bin

RUN yum install -y libtool-ltdl git

EXPOSE 8080

ENTRYPOINT /home/tomcat/apache-tomcat-7.0.55/bin/catalina.sh run