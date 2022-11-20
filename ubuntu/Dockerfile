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
    echo 'curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
apt install gh -y' > install_gh.sh && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
