FROM ubuntu:22.04

WORKDIR /app

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update

RUN apt-get install -y wget build-essential \
	libreadline-dev libncursesw5-dev libssl-dev \
	libsqlite3-dev tk-dev libgdbm-dev libc6-dev \
	libbz2-dev libffi-dev zlib1g-dev

RUN wget https://www.python.org/ftp/python/3.10.0/Python-3.10.0.tar.xz && \
	tar -xf Python-3.10.0.tar.xz && \
	cd Python-3.10.0/ && \
	./configure --prefix=/opt/python3.10 && \
	make -j$(nproc) && make altinstall && \
	cd /app && \
	rm -rf Python-3.10.0 Python-3.10.0.tar.xz

ENV PATH="/opt/python3.10/bin:$PATH"

