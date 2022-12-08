# jammy is 22.04 LTS
FROM ubuntu:jammy 

WORKDIR /root

#RUN sed -i 's@archive.ubuntu.com@ftp.jaist.ac.jp/pub/Linux@g' /etc/apt/sources.list

ENV TZ=Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && \
    apt-get install -y \
    git \
    ansible \
    sshpass \
    python3 \
    python3-pip \
    python3-distutils \
    wget \
    curl \
    vim \
    iproute2 \
    iputils-ping \
    net-tools \
    build-essential

RUN mkdir /etc/ansible &&\
    echo '[ssh_connection] \
ssh_args = -o ControlMaster=auto -o ControlPersist=60s -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null' > /etc/ansible/ansible.cfg

RUN echo 'curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
apt install gh -y' > install_gh.sh #&& \
#    apt-get clean && \
#    rm -rf /var/lib/apt/lists/*
