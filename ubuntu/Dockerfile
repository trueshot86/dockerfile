FROM ubuntu:jammy

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
