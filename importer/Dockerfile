####################################################################################################
## Builder
####################################################################################################
FROM caddy:2.4.6-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/mholt/caddy-webdav

####################################################################################################
## Final image
####################################################################################################
FROM caddy:2.4.6-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy

COPY ./importer/Caddyfile /etc/caddy/Caddyfile
