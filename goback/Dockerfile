FROM golang:alpine
MAINTAINER <garterfild14@gmail.com> Illia

#Setup dependecies and update system
RUN apk update && apk add  git g++

#Setting up GO
RUN mkdir /app
WORKDIR /app
ENV GOPATH /app
ENV GOROOT /usr/local/go/
ENV PATH $PATH:$GOROOT:$GOPATH/bin
ENV EXECPATH $GOPATH/src/github.com/gothinkster/golang-gin-realworld-example-app
#RUN git clone https://github.com/gothinkster/golang-gin-realworld-example-app /app

#Setup go dependencies
RUN go get -u github.com/kardianos/govendor && \
    go get -u github.com/pilu/fresh && \ 
    go get -u github.com/gothinkster/golang-gin-realworld-example-app

RUN cd $EXECPATH && \ 
    govendor sync 
RUN cd $EXECPATH && \
    govendor add +external 
CMD cd $EXECPATH && \
    fresh
