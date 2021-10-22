#
# Dockerfile for samba (without netbios)
#

FROM alpine: 3.12.3

RUN apk add --update \
    samba-common-tools \
    samba-client \
    samba-server \
    && rm -rf /var/cache/apk/*

EXPOSE 445/tcp

HEALTHCHECK --interval=60s --timeout=15s CMD smbclient -L \\localhost -U % -m SMB3

ENTRYPOINT ["smbd", "--foreground", "--log-stdout","--no-process-group"]
CMD []
