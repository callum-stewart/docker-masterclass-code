FROM golang:1.12.5-alpine3.9

# installing git
RUN apk update && apk upgrade && \
    apk add --no-cache git

WORKDIR /work
COPY ./src /work/
RUN go build -o app
CMD ["./app"]
