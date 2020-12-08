FROM golang:1.10-alpine as builder
LABEL maintainer="will835559313@163.com"
COPY . /app
WORKDIR /app
RUN apk update 
RUN apk add git
RUN go get github.com/gin-gonic/gin
RUN go build

FROM alpine:latest
WORKDIR /app
COPY --from=builder /app/app .
EXPOSE 80
CMD ["./app"]
