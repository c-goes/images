ARG BUILDER=docker.io/library/caddy:2-builder
ARG RUNTIME=docker.io/library/caddy:2-alpine

FROM ${BUILDER} AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/hetzner/v2

FROM ${RUNTIME}

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
