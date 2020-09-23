FROM alpine:3.11.6

RUN apk update && apk upgrade && \
    apk add lighttpd && \
    echo "Hello, World" > /var/www/localhost/htdocs/index.html

CMD lighttpd -D -f /etc/lighttpd/lighttpd.conf

EXPOSE 80
EXPOSE 443
