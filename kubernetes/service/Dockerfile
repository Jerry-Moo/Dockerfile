# Dockerfile
FROM golang:1.18 AS builder
RUN mkdir /src
ADD . /src
WORKDIR /src


RUN go env -w GO111MODULE=auto
RUN go build -o main .

FROM ubuntu:20.04

WORKDIR /

COPY --from=builder /src/main /main
EXPOSE 3000
ENTRYPOINT ["/main"]
