FROM       java:1.7
MAINTAINER qingbo.liu<260831882@qq.com>

ENV MAVEN_VERSION 3.3.3
ENV MAVEN_HOME /opt/maven

COPY apache-maven-3.3.3-bin.tar.gz /opt/

RUN tar xzf /opt/apache-maven-3.3.3-bin.tar.gz -C /opt && \
    mv /opt/apache-maven-${MAVEN_VERSION} /opt/maven  && \
    ln -s /opt/maven/bin/mvn /usr/bin/mvn #软链接

COPY settings.xml /opt/maven/conf/settings.xml

ADD hello /hello
RUN cd /hello && \
    mvn clean install -Dmaven.wagon.http.ssl.insecure=true -Dmaven.wagon.http.ssl.allowall=true