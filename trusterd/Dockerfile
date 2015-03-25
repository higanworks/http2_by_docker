FROM ubuntu:14.04

RUN apt-get -y update
RUN apt-get -y install sudo openssh-server git curl rake bison \
    libcurl4-openssl-dev autoconf automake autotools-dev libtool \
    pkg-config zlib1g-dev libcunit1-dev libssl-dev libxml2-dev \
    libevent-dev libjansson-dev libjemalloc-dev cython python3.4-dev make g++

RUN cd /usr/local/src/ && git clone --depth 1 https://github.com/h2o/qrintf.git
RUN cd /usr/local/src/qrintf && make install PREFIX=/usr/local

RUN cd /usr/local/src/ && git clone --depth 1 git://github.com/matsumoto-r/trusterd.git
RUN cd /usr/local/src/trusterd && make && make install INSTALL_PREFIX=/usr/local/trusterd

EXPOSE 8080

WORKDIR /usr/local/trusterd
ENTRYPOINT ["./bin/trusterd"]
CMD ["./conf/trusterd.conf.rb"]

