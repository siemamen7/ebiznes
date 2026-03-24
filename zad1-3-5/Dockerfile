FROM ubuntu:24.04

WORKDIR /app

RUN apt-get update && \
	apt-get install -y openjdk-8-jdk kotlin && \
	rm -rf /var/lib/apt/lists/*

RUN java -version && kotlinc -version
