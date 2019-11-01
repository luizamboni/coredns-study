FROM golang:1.13.3

RUN git clone --branch v1.6.4 https://github.com/coredns/coredns.git
RUN pwd 
WORKDIR /go/coredns

RUN go build

CMD ["./coredns"]