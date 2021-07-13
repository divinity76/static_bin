FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive 
RUN apt-get update -y \
    && apt-get install -y gcc \
        build-essential \
        make \ 
        cmake \
        autoconf \
        git \
        automake \
        libtool \
        libncurses5-dev \
        libcurl4-gnutls-dev \ 
        pkgconf \
        libgnutls28-dev \
        bison \
        libxml2-dev 
RUN cd / && git clone -b 'OpenSSL_1_1_1k' --single-branch --depth 1 https://github.com/openssl/openssl \
    && cd openssl \
    && ./config no-shared enable-ssl2 enable-ssl3 enable-ssl3-method \
    && make -j $(nproc) \
    && mkdir lib \
    && cp *.a lib
RUN cd / \
    && git clone -b '10.0' --single-branch --depth 1 https://github.com/MariaDB/server.git \
    && cd server \
    && mkdir build  \
    && cd /server/build \
    && export CFLAGS='-static' \
    && export CPPFLAGS='-static' \
    && export LDFLAGS='-static' \
    && cmake .. -Dwith-ssl=system -Dopenssl-dir=/openssl \
    && cd client \
    && make -j $(nproc) \
    && cp mysqldump / \
    && strip /mysqldump

