FROM debian:jessie

MAINTAINER Tobias Kohlbau<tobias.kohlbau@gmail.com>

ENV version v5.6.0

RUN apt-get -y update && \
    apt-get -y install wget xz-utils git && \
    cd /opt && \
    wget https://nodejs.org/dist/v5.6.0/node-${version}-linux-x64.tar.xz -O node.tar.xz && \
    tar xf node.tar.xz && \
    mv node-${version}-linux-x64 node && \
    ln -s /opt/node/bin/* /usr/bin/. && \
    rm -f node-${version}-linux-x64.tar.xz && \
    echo "\nexport PATH=/opt/node/bin:$PATH\nalias bower='bower --allow-root'" >> ~/.bashrc

RUN npm install -g grunt-cli
RUN npm install -g grunt
RUN npm install -g bower

WORKDIR /src

CMD ["/bin/bash"]
