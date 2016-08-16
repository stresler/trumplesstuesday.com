FROM debian:jessie 
MAINTAINER "sam@treslervania.com"

ENV GO_VERSION 1.6.3
ENV GOPATH /var/golang
ENV PATH $PATH:/usr/local/go/bin
WORKDIR /usr/local

RUN \
  apt-get update -q && \
  apt-get install -qy \
    vim \
    curl \
    git && \
  curl -O https://storage.googleapis.com/golang/go$GO_VERSION.linux-amd64.tar.gz && \
  tar -C /usr/local -xzf go$GO_VERSION.linux-amd64.tar.gz && \
  mkdir /var/golang

WORKDIR /var/golang

RUN \
  go get github.com/stresler/trumplesstuesday.com/site && \
  go install github.com/stresler/trumplesstuesday.com/site && \   

CMD [ "/var/golang/bin/site" ]
