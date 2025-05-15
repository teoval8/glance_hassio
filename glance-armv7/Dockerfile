ARG BUILD_FROM=ghcr.io/home-assistant/armv7-base:3.18
FROM ${BUILD_FROM}

RUN apk add --no-cache curl

RUN mkdir -p /config/glance && \
    curl -o /config/glance/glance.yml https://raw.githubusercontent.com/glanceapp/glance/refs/heads/main/docs/glance.yml && \
    curl -L https://github.com/glanceapp/glance/releases/latest/download/glance-linux-armv7.tar.gz -o /tmp/glance.tar.gz && \
    tar -xzvf /tmp/glance.tar.gz -C /usr/bin && \
    chmod +x /usr/bin/glance

CMD glance --config /config/glance/glance.yml
