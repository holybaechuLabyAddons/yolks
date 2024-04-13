label author="holybaechu" maintainer="holyb@holyb.xyz"

run apt update \
    && apt -y install pkg-config openssl libssl-dev \
    && useradd -m -d /home/container container

user container
env USER=container HOME=/home/container
workdir /home/container

copy ./../entrypoint.sh /entrypoint.sh
run chmod +x /entrypoint.sh
cmd ["/entrypoint.sh"]
