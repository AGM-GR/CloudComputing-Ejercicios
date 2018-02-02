FROM alpine:3.3

MAINTAINER Alejandro Guerrero Martínez

WORKDIR /microservice

RUN apk --update add python py-pip

RUN pip install flask flask-restful flask-jsonpify flask-cors

COPY status.py /microservice

EXPOSE 5000

ENTRYPOINT python status.py
