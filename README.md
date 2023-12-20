# xxhash-safe

The package is a fork and removes assembly and unsafe implementations.


[![Go Reference](https://pkg.go.dev/badge/github.com/amattn/xxhash-safe/v2.svg)](https://pkg.go.dev/github.com/amattn/xxhash-safe/v2)
[![Test](https://github.com/cespare/xxhash/actions/workflows/test.yml/badge.svg)](https://github.com/cespare/xxhash/actions/workflows/test.yml)

xxhash is a Go implementation of the 64-bit [xxHash] algorithm, XXH64. This is a
high-quality hashing algorithm that is much faster than anything in the Go
standard library.

This package provides a straightforward API:

```
func Sum64(b []byte) uint64
func Sum64String(s string) uint64
type Digest struct{ ... }
    func New() *Digest
```

The `Digest` type implements hash.Hash64. Its key methods are:

```
func (*Digest) Write([]byte) (int, error)
func (*Digest) WriteString(string) (int, error)
func (*Digest) Sum64() uint64
```


[xxHash]: http://cyan4973.github.io/xxHash/

## Compatibility

This package is in a module and the latest code is in version 2 of the module.
You need a version of Go with at least "minimal module compatibility" to use
github.com/amattn/xxhash-safe/v2:

* 1.9.7+ for Go 1.9
* 1.10.3+ for Go 1.10
* Go 1.11 or later

I recommend using the latest release of Go.

