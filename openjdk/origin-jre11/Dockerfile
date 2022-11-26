FROM openjdk:11-jre

LABEL io.meshware.image.author="chenzhiguo@live.com"
USER root

ENV TZ Asia/Shanghai

RUN sed -i 's/deb.debian.org/mirrors.aliyun.com/g' /etc/apt/sources.list

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