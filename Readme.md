Steps to reproduce:

```
cd /tmp
git clone https://github.com/psanford/gobug34068
cd gobug34068
GOPATH=$(pwd)

# works
go1.12 install example.com/foo

# fails
go1.13 install example.com/foo
```

The error from the go1.13 install is:
```
src/vendor/golang.org/x/net/http2/frame.go:17:2: use of vendored package not allowed
/home/psanford/lib/go1.13/src/net/http/h2_bundle.go:49:2: use of vendored package not allowed
src/vendor/golang.org/x/net/http2/transport.go:36:2: use of vendored package not allowed
```
