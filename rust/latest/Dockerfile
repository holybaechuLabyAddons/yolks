from --platform=$TARGETOS/$TARGETARCH rust:slim

label author="holybaechu" maintainer="holyb@holyb.xyz"

run apt update \
    && apt -y install pkg-config openssl libssl-dev \
    && useradd -m -d /home/container container

user container
env USER=container HOME=/home/container CARGO_HOME=/home/container/.cargo
workdir /home/container

copy --chown=container:container ./../entrypoint.sh /entrypoint.sh
run chmod +x /entrypoint.sh
entrypoint ["/usr/bin/tini", "-g", "--"]
cmd ["/entrypoint.sh"]
