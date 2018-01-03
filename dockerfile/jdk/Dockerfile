# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM          centos:7.1.1503
MAINTAINER   qingbo.liu<260831882@qq.com>

#注意，dockerfile和jdk压缩文件要在同一目录
ADD jdk-7u80-linux-x64.tar.gz /home/jdk/

ENV JAVA_VERSION 1.7.0_80
ENV JAVA_HOME /home/jdk/jdk1.7.0_80

ENV PATH $PATH:$JAVA_HOME/bin