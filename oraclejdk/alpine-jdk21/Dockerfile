FROM --platform=$TARGETPLATFORM alpine:latest
ARG TARGETPLATFORM
ARG BUILDPLATFORM
ARG TARGETARCH
LABEL image.author="chenzhiguo@live.com"
USER root

ENV TZ Asia/Shanghai

RUN sed -i "s/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g" /etc/apk/repositories \
    && apk update \
    && apk add --no-cache tzdata \
    && apk add --no-cache bash \
    && apk add --no-cache curl \
    && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone \
    && rm -rf /var/cache/apk/*

COPY ./jdk-21_linux-${TARGETARCH}_bin.tar.gz /usr/local
RUN tar -zxvf /usr/local/jdk-21_linux-${TARGETARCH}_bin.tar.gz -C /usr/local && rm -rf /usr/local/*.tar.gz

ENV JAVA_HOME /usr/local/jdk-21.0.6
ENV PATH $JAVA_HOME/bin:$PATH