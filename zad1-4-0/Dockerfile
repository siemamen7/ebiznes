FROM ubuntu:24.04

WORKDIR /app

COPY build.gradle /app

RUN apt-get update && \
	apt-get install -y openjdk-8-jdk openjdk-17-jdk kotlin wget && \
	rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH=$JAVA_HOME/bin:$PATH

RUN wget https://services.gradle.org/distributions/gradle-9.4.0-bin.zip && \
	unzip gradle-9.4.0-bin.zip && \
	ln -s /app/gradle-9.4.0/bin/gradle /usr/bin/gradle && \
	rm gradle-9.4.0-bin.zip

RUN java -version && kotlinc -version && gradle --version