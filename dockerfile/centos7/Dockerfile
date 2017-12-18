# MAINTAINER        qingbo.liu<260831882@qq.com>
# DOCKER-VERSION    17.06.2-ce

FROM        centos:7.1.1053
MAINTAINER  qingbo.liu<260831882@qq.com>

#时区
ENV TZ "Asia/Shanghai"
#虚拟终端
ENV TERM xterm

ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN yum install -y curl wget tar bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \
    yum install -y gcc gcc-c++ git make automake cmake patch logrotate python-devel libpng-devel libjpeg-devel && \
    yum install -y --enablerepo=epel pwgen python-pip && \
    yum clean all

#进程管理工具（supervisor：管理人）：Linux的后台进程运行有好几种方法，例如nohup，screen等，但是，如果是一个服务程序，要可靠
#地在后台运行，我们就需要把它做成daemon，最好还能监控进程状态，在意外结束时能自动重启。supervisor是用Python开发的一套通用的
#进程管理工具，能将一个普通的命令行进程变为后台daemon，并监控进程状态，异常退出时能自动重启，可以很方便的用来启动、重启、关
#闭进程（不仅仅是 Python 进程），除了对单个进程的控制，还可以同时启动、关闭多个进程，比如很不幸的服务器出问题导致所有应用程序
#都被杀死，此时可以用 supervisor 同时启动所有应用程序而不是一个一个地敲命令启动。
RUN pip install supervisor
#添加supervisor主配置文件
ADD supervisord.conf /etc/supervisord.conf
#第一个目录存放启动其他进程的配置文件，第二个目录存放supervisord日志
RUN mkdir -p /etc/supervisor.conf.d && \
    mkdir -p /var/log/supervisor

EXPOSE 22

ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
