FROM alpine:3.11.6

RUN apk update && apk upgrade && \
    apk add lighttpd && \
    mkdir -p /var/www/html && echo "Hello, World" > /var/www/html/index.html && \ 
    mkdir -p /var/cache/lighttpd/compress/

COPY ./lighttpd.conf /etc/lighttpd/lighttpd.conf

CMD lighttpd -D -f /etc/lighttpd/lighttpd.conf

EXPOSE 80
EXPOSE 443
