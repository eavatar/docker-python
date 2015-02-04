FROM ubuntu:14.04.1

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update
RUN apt-get install -y python2.7-minimal

RUN mkdir /dist
WORKDIR /dist

RUN mkdir -p lib etc/ssl etc/ca-certificates usr/bin usr/lib/python2.7
RUN cp /usr/bin/python2.7 usr/bin/python
#RUN cp /usr/bin/pip  usr/bin/pip
#RUN cp /etc/ca-certificates.conf etc/
#RUN cp -r /etc/ca-certificates/* etc/ca-certificates/
#RUN cp -r /etc/ssl/* etc/ssl/

RUN cp -r /usr/lib/python2.7/* usr/lib/python2.7/
RUN find . -type f -name "*.py" -exec rm -f {} \;
RUN cp /lib/x86_64-linux-gnu/libutil.so.1 lib/
RUN cp /lib/x86_64-linux-gnu/libz.so.1 lib/
RUN cp /lib/x86_64-linux-gnu/libssl.so.1.0.0 lib/
RUN cp /lib/x86_64-linux-gnu/libcrypt.so.1 lib/
RUN cp /lib/x86_64-linux-gnu/libcrypto.so.1.0.0 lib/
RUN cp /lib/x86_64-linux-gnu/libreadline.so.6 lib/
RUN cp /lib/x86_64-linux-gnu/libexpat.so.1 lib/
RUN cp /usr/lib/x86_64-linux-gnu/libffi.so.6 usr/lib

RUN tar cf /overlayfs.tar .
