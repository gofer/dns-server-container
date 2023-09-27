FROM alpine:latest

COPY nsd.conf /etc/nsd/nsd.conf
COPY zones/ /etc/nsd/

RUN chmod 644 /etc/nsd/nsd.conf \
 && chown -R nsd:nsd /etc/nsd

CMD nsd-control start && tail -f /dev/null 
