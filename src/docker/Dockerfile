###
#
#   Version 1.4.2
#	Yves Vindevogel (vindevoy)
#	2022-02-14
#
#	Features: anonymous pypiserver
#             version is synced with the version of pypiserver
#
###
 
FROM vindevoy/debian-base:11.2

LABEL maintainer="Yves Vindevogel (vindevoy) - yves.vindevogel@asynchrone.com"

ENV DEBIAN_FRONTEND noninteractive
ENV INSTALL_VERSION 1.4.2

COPY resources/favicon.ico /tmp

RUN apt-get update -y
RUN apt-get dist-upgrade -y

RUN apt-get install python3 pip --no-install-recommends -y
RUN pip install pypiserver==$INSTALL_VERSION

RUN ln -sf /usr/bin/python3 /usr/bin/python

RUN mkdir -p /opt/packages
RUN mv /tmp/favicon.ico /opt/packages

RUN apt-get autoremove
RUN apt-get clean all

EXPOSE 8080

VOLUME /opt/packages

# -P . -a . are the secrets to having anonymous access (see the manuals)
CMD ["pypi-server", "-p", "8080", "-i", "0.0.0.0", "-P", ".", "-a", ".", "/opt/packages"]

