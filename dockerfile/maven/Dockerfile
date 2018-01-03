# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          jdk:1.7
MAINTAINER   qingbo.liu<260831882@qq.com>

ADD ./apache-maven-3.3.3-bin.tar.gz /home/maven/
COPY ./settings.xml /home/maven/apache-maven-3.3.3/conf/settings.xml

ENV MAVEN_VERSION 3.3.3
ENV M2_HOME /home/maven/apache-maven-3.3.3
ENV PATH $PATH:$M2_HOME/bin

