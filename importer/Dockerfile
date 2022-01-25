####################################################################################################
## Builder
####################################################################################################
FROM caddy:2.4.6-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/mholt/caddy-webdav

####################################################################################################
## Final image
####################################################################################################
FROM ghcr.io/silkkycloud/caddy:2.4.6

COPY --from=builder --chown=caddy:caddy /usr/bin/caddy /usr/bin/caddy

COPY --chown=caddy:caddy ./Importer/Caddyfile /etc/caddy/Caddyfile
