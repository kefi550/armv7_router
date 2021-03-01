FROM alpine:latest

RUN rm -rf /var/cache/apk* && \
    rm -rf /tmp/*

RUN apk add --update --no-cache unbound openssl && \
    wget -q https://www.internic.net/domain/named.cache -O /etc/unbound/root.hints && \
    unbound-control-setup -d /

CMD ["/usr/sbin/unbound", "-d", "-c", "/unbound.conf"]
