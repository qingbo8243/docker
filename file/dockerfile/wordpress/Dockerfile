# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce
# Dockerizing CentOS7: Dockerfile for building CentOS images

from csphere/php-fpm:5.4

add init.sh /init.sh

entrypoint ["/init.sh", "/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
