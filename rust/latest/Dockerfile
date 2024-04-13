from ghcr.io/parkervcp/yolks:debian

label author="holybaechu" maintainer="holyb@holyb.xyz"

run sudo apt update \
    && sudo apt -y install pkg-config openssl libssl-dev \
    && sudo useradd -m -d /home/container container

user container
env USER=container HOME=/home/container
workdir /home/container

copy --chown=container:container ./../entrypoint.sh /entrypoint.sh
run chmod +x /entrypoint.sh
entrypoint ["/usr/bin/tini", "-g", "--"]
cmd ["/entrypoint.sh"]
