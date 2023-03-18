FROM debian:11

ARG STATE
ARG PRIORITY
ARG VIP

RUN \
    sed -i "s/deb.debian.org/mirror.sjtu.edu.cn/g" /etc/apt/sources.list \
    && apt update \
    && apt install nginx vim procps keepalived iputils-ping curl iproute2 gettext-base supervisor -y

COPY ./keepalived.conf.template /etc/keepalived/keepalived.conf.template
RUN envsubst < /etc/keepalived/keepalived.conf.template > /etc/keepalived/keepalived.conf

RUN echo ${STATE} > /var/www/html/index.nginx-debian.html

COPY ./supervisord.conf /etc/supervisor/supervisord.conf

CMD [ "supervisord", "-c", "/etc/supervisor/supervisord.conf" ]
