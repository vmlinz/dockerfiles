#
# Dockerfile for python3
#

FROM alpine
MAINTAINER kev <noreply@datageek.info>

RUN apk add -U curl python3 \
    && curl -sSL https://bootstrap.pypa.io/get-pip.py | python3 \
    && rm -rf /var/cache/apk/*

CMD ["python3"]
