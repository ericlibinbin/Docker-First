#
# MAINTAINER        Carson,C.J.Zeong <zcy@nicescale.com>
# DOCKER-VERSION    1.6.2
#
# Dockerizing Mariadb: Dockerfile for building Mariadb images
#
FROM eric/centos:7.2
MAINTAINER eric_li<eric_libinbin@163.com>

ENV DATA_DIR /var/lib/mysql

# Install Mariadb
RUN yum install -y mariadb mariadb-server && \
    yum clean all

ADD mysqld_charset.cnf /etc/my.cnf.d/

COPY scripts /scripts
RUN chmod +x /scripts/start
RUN chmod +x /scripts/firstrun_maria
EXPOSE 3306

VOLUME ["/var/lib/mysql"]

ENTRYPOINT ["/scripts/start"]
