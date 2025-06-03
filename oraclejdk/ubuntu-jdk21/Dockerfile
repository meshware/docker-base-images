FROM --platform=$TARGETPLATFORM ubuntu:22.04
ARG TARGETPLATFORM
ARG BUILDPLATFORM
ARG TARGETARCH
LABEL image.author="chenzhiguo@live.com"
USER root

ENV TZ=Asia/Shanghai

RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak \
    && sed -i 's/archive.ubuntu.com\/ubuntu/mirrors.aliyun.com\/ubuntu/g' /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        net-tools \
        unzip \
        iputils-ping \
        netcat \
        procps \
        iproute2 \
        curl \
        wget \
    && echo "Asia/Shanghai" > /etc/timezone \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && rm -rf /var/lib/apt/lists/*

COPY ./jdk-21_linux-${TARGETARCH}_bin.tar.gz /usr/local
RUN tar -zxvf /usr/local/jdk-21_linux-${TARGETARCH}_bin.tar.gz -C /usr/local && rm -rf /usr/local/*.tar.gz

ENV JAVA_HOME=/usr/local/jdk-21.0.6
ENV PATH=$JAVA_HOME/bin:$PATH