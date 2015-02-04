FROM ubuntu:14.04.1

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get install -y python2.7 openssl python-pip python-virtualenv

#ADD requirements.txt /
#RUN pip install -r /requirements.txt

RUN mkdir -p /dist

WORKDIR /dist

RUN mkdir -p lib etc/ssl etc/ca-certificates \
    usr/local/bin usr/local/lib usr/bin usr/lib/python2.7 \
    usr/include/

RUN \
    cp /usr/bin/python2.7 usr/bin/python &&\
    cp /usr/bin/pip  usr/bin/pip &&\
    cp /usr/bin/env  usr/bin/env &&\
    cp -r /etc/ssl/* etc/ssl/ &&\
    cp -r /usr/lib/python2.7/* usr/lib/python2.7/

RUN find . -type f -name "*.py" -exec rm -f {} \;

# copy shared libraries
RUN \
    cp /lib/x86_64-linux-gnu/libutil.so.1 lib/ &&\
    cp /lib/x86_64-linux-gnu/libcrypt.so.1 lib/ &&\
    cp /lib/x86_64-linux-gnu/libreadline.so.6 lib/ &&\
    cp /lib/x86_64-linux-gnu/libexpat.so.1 lib/ &&\
    cp /lib/x86_64-linux-gnu/libcrypt.so.1 lib/ && \
    cp /lib/x86_64-linux-gnu/libpcre.so.3 lib/ && \
    cp /lib/x86_64-linux-gnu/libcrypto.so.1.0.0 lib/ && \
    cp /lib/x86_64-linux-gnu/libssl.so.1.0.0 lib/ && \
    cp /lib/x86_64-linux-gnu/libcrypto.so.1.0.0 lib/ && \
    cp /lib/x86_64-linux-gnu/libz.so.1 lib/ && \
    cp /lib/x86_64-linux-gnu/libgpg-error.so.0 lib/ && \
    cp /lib/x86_64-linux-gnu/liblzma.so.5 lib/ && \
    cp /lib/x86_64-linux-gnu/libgcrypt.so.11 lib/ && \
    cp /lib/x86_64-linux-gnu/libpng12.so.0 lib/ && \
    cp /lib/x86_64-linux-gnu/libexpat.so.1 lib/ && \
    cp /lib/x86_64-linux-gnu/libresolv.so.2 lib/ && \
    cp /lib/x86_64-linux-gnu/libcrypto.so.1.0.0 lib/ && \
    cp /lib/x86_64-linux-gnu/libbz2.so.1.0 lib/ && \
    cp /lib/x86_64-linux-gnu/liblzma.so.5 lib/ && \
    cp /lib/x86_64-linux-gnu/libgcc_s.so.1 lib/ && \
    cp /lib/x86_64-linux-gnu/libtinfo.so.5 lib/ && \
    cp /lib/x86_64-linux-gnu/libreadline.so.6 lib/

RUN \
    cp /usr/lib/x86_64-linux-gnu/libdb-5.3.so usr/lib/ && \
    cp /usr/lib/x86_64-linux-gnu/libstdc++.so.6 usr/lib/ && \
    cp /usr/lib/x86_64-linux-gnu/libsqlite3.so.0 usr/lib/


RUN tar cf /overlayfs.tar .
