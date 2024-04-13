from ghcr.io/pterodactyl/yolks:debian

label author="holybaechu" maintainer="holyb@holyb.xyz"

run apt -y update \
    && apt -y install pkg-config openssl libssl-dev

copy --chown=container:container ./../entrypoint.sh /entrypoint.sh
run chmod +x /entrypoint.sh
entrypoint ["/usr/bin/tini", "-g", "--"]
cmd ["/entrypoint.sh"]
