FROM alpine:latest

COPY unbound.conf /etc/unbound/unbound.conf

RUN chmod 644 /etc/unbound/unbound.conf \
 && chown -R unbound:unbound /etc/unbound

CMD unbound-control start && tail -f /dev/null 
