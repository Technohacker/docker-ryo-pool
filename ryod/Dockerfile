FROM debian:stretch-slim

RUN useradd -d /opt/ryod -m -s /bin/bash ryod

RUN mkdir /opt/ryod/.ryo && chown ryod:ryod /opt/ryod/.ryo

USER ryod
WORKDIR /opt/ryod

ADD bin/* /opt/ryod/

EXPOSE 19733
EXPOSE 19734

CMD /opt/ryod/ryod --rpc-bind-ip 0.0.0.0
