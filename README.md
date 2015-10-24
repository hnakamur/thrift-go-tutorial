thrift-go-tutorial
==================

This repository is my result for trying out [Apache Thrift tutorial for Go](https://thrift.apache.org/tutorial/go).

These files below are copied from https://github.com/apache/thrift/tree/b343feee0d048e214c93bd78560af9185531c094/tutorial and modified.

* tutorial.thrift
* shared.thrift
* server.crt
* server.key
* src/*.go

## Prerequisite

### Install thrift

I used [Homebrew](http://brew.sh/index.html) to install thrift.

```
brew install thrift
```

### Install thrift go library

Unfortunately thrift go library is not go-gettable. Run the following commands instead.

```
mkdir -p "$GOPATH/src/git.apache.org/thrift.git"
curl -sL https://github.com/apache/thrift/archive/master.tar.gz | tar xf - --strip-component 1 -C "$GOPATH/src/git.apache.org/thrift.git/" thrift-master/lib/go/
```

## How to build

### Generate go sources from thrift IDL sources

```
thrift -gen go:package_prefix=github.com/hnakamur/thrift-go-tutorial/gen-go/ tutorial.thrift
thrift -gen go:package_prefix=github.com/hnakamur/thrift-go-tutorial/gen-go/ shared.thrift
```

### Build generated go sources

```
(cd gen-go/tutorial && go build)
```
