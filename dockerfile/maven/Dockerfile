# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          centos:7.1.1503
MAINTAINER   qingbo.liu<260831882@qq.com>

COPY ./apache-maven-3.3.3-bin.tar.gz /home/maven/
COPY ./settings.xml /home/maven/apache-maven-3.3.3/conf/settings.xml

ENV MAVEN_VERSION 3.3.3
ENV M2_HOME /home/maven/apache-maven-3.3.3
ENV PATH $PATH:$M2_HOME/bin

ADD ./hello /home/hello
RUN cd /home/hello && \
    mvn clean install -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true