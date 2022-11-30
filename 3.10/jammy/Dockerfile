FROM ubuntu:22.04

LABEL org.opencontainers.image.authors="Kirill Shtrykov <kirill@shtrykov.com>"
LABEL org.opencontainers.image.url=https://github.com/kirill-shtrykov/python-docker

ENV TZ=Europe/Minsk

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt update && apt install -y software-properties-common curl build-essential

RUN apt update && apt install -y python3.10 python3.10-distutils python3.10-dev \
    && apt clean \
    && update-alternatives --install /usr/bin/python python $(which python3.10) 100

RUN curl https://bootstrap.pypa.io/get-pip.py -o /tmp/get-pip.py && python /tmp/get-pip.py && rm -rf /tmp/*
