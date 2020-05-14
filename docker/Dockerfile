FROM balenalib/rpi-raspbian:buster

RUN apt-get update && apt-get install -y wget

RUN wget http://nginx.org/keys/nginx_signing.key && \
  apt-key add nginx_signing.key && \
  echo "deb http://nginx.org/packages/debian/ buster nginx" >> /etc/apt/sources.list && \
  echo "deb-src http://nginx.org/packages/debian/ buster nginx" >> /etc/apt/sources.list && \
  apt-get update && apt-get install -y nginx

RUN apt-get -y clean \
  && rm -rf /var/lib/apt/lists/*

EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"]
