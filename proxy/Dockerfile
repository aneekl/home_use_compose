FROM caddy:2.10.0-builder AS builder

ENV GOTOOLCHAIN=
RUN xcaddy build v2.10.0 \
    --with github.com/caddy-dns/desec \
    --with github.com/lucaslorentz/caddy-docker-proxy/v2

FROM caddy:2.10.0

COPY --from=builder /usr/bin/caddy /usr/bin/caddy

CMD ["caddy", "docker-proxy"]