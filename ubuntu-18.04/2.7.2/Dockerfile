FROM ubuntu:18.04

USER root

RUN apt-get update \
 && apt-get install -y \
	    vim-tiny \
	    flip \
      ca-certificates \
      iputils-ping \
      libssl-dev \
      libssl1.0.0 \
      curl \
 && apt-get -y clean \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /home/duplicacy

ENV DUPLICACY_URL="https://github.com/gilbertchen/duplicacy/releases/download/v2.7.2/duplicacy_linux_x64_2.7.2"
RUN curl -Lso /usr/local/bin/duplicacy ${DUPLICACY_URL} && \
    chmod +x /usr/local/bin/duplicacy

ENTRYPOINT ["/usr/local/bin/duplicacy"]
