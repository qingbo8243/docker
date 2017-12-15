# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce
# Dockerizing CentOS7: Dockerfile for building CentOS images

FROM       centos/centos7:7.1
MAINTAINER qingbo.liu<260831882@qq.com>

ENV DATA_DIR /var/lib/mysql

# Install Mariadb
RUN  rpm --rebuilddb && \
     yum install -y mariadb mariadb-server && \
     yum clean all

ADD mysqld_charset.cnf /etc/my.cnf.d/

COPY scripts /scripts
RUN chmod +x /scripts/start

EXPOSE 3306

#将数据库的数据保留下来
VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]
