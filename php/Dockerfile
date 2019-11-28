FROM aboutphp/centos7

ARG PHPVERSION=70

RUN yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm \
    \
     && yum-config-manager -y --enable remi-php${PHPVERSION} \
     \
       && yum -y install php httpd \
        \
         && systemctl enable httpd.service

COPY config/v-host.conf /etc/httpd/conf.d/

RUN mkdir -p /var/www/website

EXPOSE 80
CMD ["/usr/sbin/init"]