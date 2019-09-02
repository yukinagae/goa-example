# goa-example

goa example project

## Requirements

- go: 1.12.9

## Setup

```bash
go get -u goa.design/goa/v3
go get -u goa.design/goa/v3/...
go get -u github.com/golang/protobuf/protoc-gen-go # for gRPC
```

## Generate files

```bash
goa gen calcsvc/design
goa example calcsvc/design
```

## Start server

### On local

Build

```bash
go build ./cmd/calc && go build ./cmd/calc-cli
```

Run server

```bash
./calc
```

### On docker

```bash
docker-compose up
```

(Build again if Dockerfile is being changed)

```bash
docker-compose build
```

## Play with it

HTTP

```bash
./calc-cli --url="http://localhost:8080" calc add --a 1 --b 2
```

gRPC

```bash
./calc-cli --url="grpc://localhost:8080" calc add --message '{"a": 1, "b": 2}'
```

## References

- [goa - Getting Started](https://goa.design/learn/getting-started/)
