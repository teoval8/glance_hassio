ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:3.18
FROM ${BUILD_FROM}

RUN apk add --no-cache docker-cli curl

RUN mkdir -p /config/glance
RUN curl -o /config/glance/glance.yml https://raw.githubusercontent.com/glanceapp/glance/refs/heads/main/docs/glance.yml

COPY docker-compose.yml /config/glance/docker-compose.yml

CMD docker compose -f /config/glance/docker-compose.yml up -d && tail -f /dev/null
