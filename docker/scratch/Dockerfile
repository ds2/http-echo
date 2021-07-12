FROM golang:latest as buildr
WORKDIR /src
ADD . .
RUN rm -r gopath; go build -o http-echo

FROM gcr.io/distroless/base
LABEL maintainer "Seth Vargo <seth@sethvargo.com> (@sethvargo)"
#ADD "https://curl.haxx.se/ca/cacert.pem" "/etc/ssl/certs/ca-certificates.crt"
COPY --from=buildr "/src/http-echo" "/"
USER 1000
ENTRYPOINT ["/http-echo"]
