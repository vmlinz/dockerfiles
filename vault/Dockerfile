#
# Dockerfile for vault
#

FROM alpine
MAINTAINER kev <noreply@datageek.info>

ENV VAULT_VER 0.3.0
ENV VAULT_URL http://dl.bintray.com/mitchellh/vault/vault_${VAULT_VER}_linux_amd64.zip
ENV VAULT_MD5 4fb2da2ffd7733a1cfeb6a97023e45d5
ENV VAULT_FILE vault.zip
ENV VAULT_ADDR https://127.0.0.1:8200

RUN wget -O $VAULT_FILE $VAULT_URL \
    && echo "$VAULT_MD5  $VAULT_FILE" | md5sum -c \
    && unzip $VAULT_FILE -d /usr/bin/ \
    && chmod +x /usr/bin/vault \
    && rm $VAULT_FILE

COPY vault /etc/vault

VOLUME /etc/vault /var/lib/vault

EXPOSE 8200

CMD ["vault", "server", "-config=/etc/vault/vault.hcl"]
