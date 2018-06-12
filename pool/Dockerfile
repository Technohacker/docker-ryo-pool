FROM node:8-slim

RUN useradd -d /opt/pool -m -s /bin/bash pool

RUN apt-get update && apt-get install -y \
    git \
    gcc \
    g++ \
    make \
    libboost-all-dev \
    python \
 && rm -rf /var/lib/apt/lists/*

USER pool
WORKDIR /opt/pool

ADD cryptonote-ryo-pool/ config.json /opt/pool/

RUN npm install

CMD until curl http://ryo-wallet:19735/json_rpc ; do sleep 1; done; node init.js
