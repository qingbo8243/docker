# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          tomcat:7
MAINTAINER   qingbo.liu<260831882@qq.com>

COPY jenkins.war $APP_DIR

ENV JAVA_HOME /home/jdk/jdk1.8.0_151
ENV PATH $PATH:$JAVA_HOME/bin

EXPOSE 8080

ENTRYPOINT /home/tomcat/apache-tomcat-7.0.55/bin/catalina.sh run