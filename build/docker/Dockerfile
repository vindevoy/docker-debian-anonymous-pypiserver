FROM vindevoy/debian-base:11.2

LABEL maintainer="Yves Vindevogel (vindevoy) - yves.vindevogel@asynchrone.com"

ENV DEBIAN_FRONTEND noninteractive
ENV INSTALL_VERSION 1.4.2

COPY resources/favicon.ico /tmp

RUN set -x && \ 
    apt-get update -y && \ 
    apt-get dist-upgrade -y && \ 
    apt-get install python3 pip --no-install-recommends -y && \ 
    pip install pypiserver==$INSTALL_VERSION && \ 
    ln -sf /usr/bin/python3 /usr/bin/python && \ 
    mkdir -p /opt/packages && \ 
    mv /tmp/favicon.ico /opt/packages && \ 
    apt-get autoremove && \ 
    apt-get clean all

EXPOSE 8080

VOLUME /opt/packages

CMD ["pypi-server", "-p", "8080", "-i", "0.0.0.0", "-P", ".", "-a", ".", "/opt/packages"]
