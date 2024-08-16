FROM debian:bookworm-backports

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y dist-upgrade && \
    apt install -y \
        ca-certificates \
        sudo \
        build-essential \
        curl \
        git \
        wget \
        p7zip-full \
        python3 \
        binfmt-support \
        qemu-system \
        qemu-user \
        qemu-user-static \
        file \
        fdisk \
        btrfs-progs \
        jq \
        zip \
        xz-utils \
        lsof \
        psmisc && \
    rm -rf /var/lib/apt/lists/*

RUN ln -s /usr/bin/python3 /usr/bin/python

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8' TERM=screen

WORKDIR /opt/custompios
