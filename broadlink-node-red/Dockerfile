FROM debian:stretch
ARG CPUCORE="1"

RUN apt-get update && \
    apt-get -y install curl git python3-dev python3-pip && \
    cd /usr/local/ && \
    git clone https://github.com/mjg59/python-broadlink.git && \
    pip3 install broadlink && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
    apt-get update && \
    apt-get -y install nodejs && \ 
    npm install -g --unsafe-perm node-red

WORKDIR /usr/local/python-broadlink

ENTRYPOINT node-red --max-old-space-size=256
