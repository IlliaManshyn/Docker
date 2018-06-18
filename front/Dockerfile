FROM alpine:3.6
MAINTAINER <garterfild14@gmail.com> Illia

RUN apk update && \
    apk add git nodejs-npm
RUN git clone https://github.com/gothinkster/react-redux-realworld-example-app
RUN cd react-redux-realworld-example-app && \
    npm install
CMD cd react-redux-realworld-example-app && \
    npm start
