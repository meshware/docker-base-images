FROM --platform=$TARGETPLATFORM hub.jdcloud.com/baseimages/openeuler:22.03lts-${TARGETARCH}-depends-tools-v20230810
ARG TARGETPLATFORM
ARG BUILDPLATFORM
ARG TARGETARCH
LABEL image.author="chenzhiguo@live.com"
USER root

ENV TZ Asia/Shanghai

RUN echo "Asia/Shanghai" > /etc/timezone \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

COPY ./jdk-11.0.21_linux-${TARGETARCH}_bin.tar.gz /usr/local
RUN tar -zxvf /usr/local/jdk-11.0.21_linux-${TARGETARCH}_bin.tar.gz -C /usr/local && rm -rf /usr/local/*.tar.gz

ENV JAVA_HOME /usr/local/jdk-11.0.21
ENV PATH $JAVA_HOME/bin:$PATH