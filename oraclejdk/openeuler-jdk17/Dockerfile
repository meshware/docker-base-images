FROM --platform=$TARGETPLATFORM hub.jdcloud.com/baseimages/openeuler:22.03lts-${TARGETARCH}-depends-tools-v20230810
ARG TARGETPLATFORM
ARG BUILDPLATFORM
ARG TARGETARCH
LABEL image.author="chenzhiguo@live.com"
USER root

ENV TZ Asia/Shanghai

RUN echo "Asia/Shanghai" > /etc/timezone \
    && ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

RUN sudo yum install -y unzip;

# Download first from https://javadl.oracle.com/webapps/download/GetFile/1.8.0_331-b09/165374ff4ea84ef0bbd821706e29b123/linux-i586/jre-8u331-linux-x64.tar.gz
COPY ./jdk-17_linux-${TARGETARCH}_bin.tar.gz /usr/local
RUN tar -zxvf /usr/local/jdk-17_linux-${TARGETARCH}_bin.tar.gz -C /usr/local && rm -rf /usr/local/*.tar.gz

ENV JAVA_HOME /usr/local/jdk-17.0.9
ENV PATH $JAVA_HOME/bin:$PATH