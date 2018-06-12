FROM debian:stretch-slim

RUN useradd -d /opt/ryowallet -m -s /bin/bash ryowallet

ADD bin/* /opt/ryowallet/
ADD pool pool.address.txt pool.keys pool-passwd /opt/ryowallet/

RUN chown ryowallet:ryowallet /opt/ryowallet/pool*

USER ryowallet
WORKDIR /opt/ryowallet

EXPOSE 19735

CMD /opt/ryowallet/ryo-wallet-rpc --rpc-bind-port 19735 --rpc-bind-ip 0.0.0.0 --wallet-file /opt/ryowallet/pool --password-file /opt/ryowallet/pool-passwd --daemon-host ryod --confirm-external-bind
