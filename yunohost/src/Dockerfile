FROM ubuntu:jammy

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y dist-upgrade && \
    apt install -y \
        binfmt-support \
        btrfs-progs \
        build-essential \
        curl \
        fdisk \
        file \
        git \
        jq \
        lsof \
        p7zip-full \
        psmisc \
        python3 \
        qemu-utils \
        qemu-user-static \
        sudo \ 
        wget \
        xz-utils \
        zip && \
    rm -rf /var/lib/apt/lists/*

ENV LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8' TERM=screen

WORKDIR /opt/custompios
