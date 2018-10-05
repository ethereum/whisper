FROM ubuntu:18.04

USER root

RUN mkdir /go
ENV GOPATH=/go
RUN apt-get update -y && apt-get install -y golang git
RUN go get github.com/ethereum/go-ethereum
RUN cd $GOPATH/src/github.com/ethereum/go-ethereum && go build ./cmd/wnode
RUN $GOPATH/src/github.com/ethereum/go-ethereum/wnode -generatekey | awk '{ print $4; }' | tee /key.txt

EXPOSE 8545 30303

ENTRYPOINT ["/go/src/github.com/ethereum/go-ethereum/wnode", "-idfile", "/key.txt", "-boot", "enode://f0fa95ee17a42b4cf5fee104c5ad61115ff63b2f720c027b1246188afc93a61ba1d67121ea9ebfa78678e796a562a5d949ed5265549f0a4936b7f3bd8d5d2706@35.170.55.156:30303", "-ip", "0.0.0.0:30303", "-test"]
