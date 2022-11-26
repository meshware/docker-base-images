FROM ubuntu:22.04

LABEL io.meshware.image.author="chenzhiguo@live.com"
USER root

ENV TZ Asia/Shanghai

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak
RUN sed -i 's/archive.ubuntu.com\/ubuntu/mirrors.aliyun.com\/ubuntu/g' /etc/apt/sources.list
RUN apt-get update; \
    apt-get install -y --no-install-recommends \
    net-tools \
    iputils-ping \
    netcat \
    procps \
    iproute2 \
    ; \
    rm -rf /var/lib/apt/lists/*

RUN echo "Asia/Shanghai" > /etc/timezone \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# Download first from https://javadl.oracle.com/webapps/download/GetFile/1.8.0_331-b09/165374ff4ea84ef0bbd821706e29b123/linux-i586/jre-8u331-linux-x64.tar.gz
COPY jre-8u331-linux-x64.tar.gz /usr/local
RUN tar -zxvf /usr/local/jre-8u331-linux-x64.tar.gz -C /usr/local && rm -rf /usr/local/*.tar.gz

ENV JAVA_HOME /usr/local/jre1.8.0_331
ENV PATH $JAVA_HOME/bin:$PATH