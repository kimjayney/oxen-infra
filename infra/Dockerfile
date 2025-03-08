FROM ubuntu:20.04

ENV TZ=Asia/Seoul
ENV container docker

RUN apt-get update && apt-get upgrade -y \
    && apt install -y init systemd \
    && apt install -y build-essential \
    && apt install -y vim curl \
    && apt install -y net-tools iputils-ping \
    && apt-get clean autoclean \
    && apt-get autoremove -y \
    && rm -rf /var/lib/{apt,dpkg,cache,log}
RUN curl -so /etc/apt/trusted.gpg.d/oxen.gpg https://deb.oxen.io/pub.gpg
RUN echo "deb https://deb.oxen.io focal main" | tee /etc/apt/sources.list.d/oxen.list
RUN apt update 
VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/sbin/init"]
