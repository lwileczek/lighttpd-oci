FROM debian:buster-slim

RUN apt-get update && apt-get -y upgrade && \
    apt-get -y install lighttpd && \
    echo "Hello, World" > /var/www/html/index.html

COPY ./lighttpd.conf /etc/lighttpd/lighttpd.conf

# RUN useradd -ms /bin/bash lighttpd-usr
# USER lighttpd-usr
# WORKDIR /home/lighttpd-usr

CMD lighttpd -D -f /etc/lighttpd/lighttpd.conf

EXPOSE 80
EXPOSE 443
