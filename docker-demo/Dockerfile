
FROM golang:1.11 AS builder
WORKDIR /go/src/docker-demo/
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o docker-demo .
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /go/src/docker-demo .
CMD ["./docker-demo"]