FROM ubuntu

MAINTAINER Tom

RUN apt-get update
RUN apt-get install gcc libc6-dev git lrzsz -y
ADD ["go1.11.linux-amd64.tar.gz","/usr/local/"]
COPY ["test.go","/root/go/src/190108/"]

ENV GOROOT=/usr/local/go
ENV GOPATH=/root/go
ENV PATH=$GOROOT/bin:$GOPATH/bin:$PATH

RUN go get github.com/astaxie/beego

WORKDIR /root/go/src/190108
ENTRYPOINT ["go","run","test.go"]

EXPOSE 8080
