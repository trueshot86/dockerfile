FROM ubuntu:jammy # jammy is 22.04 LTS

WORKDIR /root

RUN apt-get update && \
    apt-get install -y \
    git \
    python3 \
    wget \
    curl \
    vim \
    iproute2 \
    iputils-ping \
    net-tools \
    build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
