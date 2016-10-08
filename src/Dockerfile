FROM ubuntu:14.04

MAINTAINER Robby Prima Suherlan <robbiejobs@gmail.com>

RUN apt-get update && apt-get install -y wget curl supervisor

RUN wget -O - https://gist.githubusercontent.com/igez/4a27dfcaa059368815b79433765e8d63/raw/9be3bb14378588f4b797427bfc366c336e7927fd/install_mailcatcher.sh | bash

ADD ./conf/supervisor.conf /etc/supervisor/conf.d/supervisor.conf
ADD ./bootstrap.sh /bootstrap.sh

RUN chmod +x /bootstrap.sh

ENTRYPOINT ["/bin/bash", "/bootstrap.sh"]

EXPOSE 1080
EXPOSE 1025
