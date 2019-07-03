# Sentry handler

[![CircleCI](https://circleci.com/gh/emperror/handler-sentry.svg?style=svg)](https://circleci.com/gh/emperror/handler-sentry)
[![Go Report Card](https://goreportcard.com/badge/handler.emperror.dev/sentry?style=flat-square)](https://goreportcard.com/report/handler.emperror.dev/sentry)
[![GolangCI](https://golangci.com/badges/github.com/emperror/handler-sentry.svg)](https://golangci.com/r/github.com/emperror/handler-sentry)
[![GoDoc](http://img.shields.io/badge/godoc-reference-5272B4.svg?style=flat-square)](https://godoc.org/handler.emperror.dev/sentry)

**Error handler integration for [Sentry](https://sentry.com).**


## Installation

```bash
go get handler.emperror.dev/sentry
```


## Usage

```go
package main

import (
	"handler.emperror.dev/sentry"
)

func main() {
}
```


## Development

When all coding and testing is done, please run the test suite:

``` bash
$ make check
```


## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.
