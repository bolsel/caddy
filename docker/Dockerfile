# Build Caddy dengan Mercure dan Vulcain modules
FROM caddy:2-builder-alpine AS bolsel_caddy_2_builder

RUN xcaddy build \
	--with github.com/dunglas/mercure \
	--with github.com/dunglas/mercure/caddy \
	--with github.com/dunglas/vulcain \
	--with github.com/dunglas/vulcain/caddy

# Caddy image
FROM caddy:2-alpine AS bolsel_caddy_2

WORKDIR /srv/app

COPY --from=bolsel_caddy_2_builder /usr/bin/caddy /usr/bin/caddy
