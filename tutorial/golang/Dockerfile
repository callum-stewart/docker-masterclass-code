# syntax=docker/dockerfile:1
FROM golang:1.12.5-alpine3.9 as builder

# installing git
RUN apk update && apk upgrade && \
    apk add --no-cache git

COPY src .

RUN go build -o server .
CMD ["./server"]
#RUN go get github.com/sirupsen/logrus
#RUN go get github.com/buaazp/fasthttprouter
#RUN go get github.com/valyala/fasthttp
