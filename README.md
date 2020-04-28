# Sentry handler

<<<<<<< HEAD
[![CircleCI](https://circleci.com/gh/emperror/handler-sentry.svg?style=svg)](https://circleci.com/gh/emperror/handler-sentry)
[![Go Report Card](https://goreportcard.com/badge/handler.emperror.dev/sentry?style=flat-square)](https://goreportcard.com/report/handler.emperror.dev/sentry)
[![GolangCI](https://golangci.com/badges/github.com/emperror/handler-sentry.svg)](https://golangci.com/r/github.com/emperror/handler-sentry)
[![GoDoc](http://img.shields.io/badge/godoc-reference-5272B4.svg?style=flat-square)](https://pkg.go.dev/handler.emperror.dev/sentry)
=======
[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/emperror/handler-sentry/CI?style=flat-square)](https://github.com/emperror/handler-sentry/actions?query=workflow%3ACI)
[![Codecov](https://img.shields.io/codecov/c/github/emperror/handler-sentry?style=flat-square)](https://codecov.io/gh/emperror/handler-sentry)
[![Go Report Card](https://goreportcard.com/badge/emperror.dev/handler/sentry?style=flat-square)](https://goreportcard.com/report/emperror.dev/handler/sentry)
![Go Version](https://img.shields.io/badge/go%20version-%3E=1.12-61CFDD.svg?style=flat-square)
[![go.dev reference](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white&style=flat-square)](https://pkg.go.dev/mod/emperror.dev/handler/sentry)

>>>>>>> Update package

**Error handler integration for [Sentry](https://sentry.com).**


## Installation

```bash
go get emperror.dev/handler/sentry
```


## Usage

```go
package main

import (
	"emperror.dev/handler/sentry"
)

func main() {
	dsn := "https://user:password@sentry.io/1234"

	handler, err := sentry.New(dsn)
	if err != nil {
		panic(err)
	}
	defer handler.Close() // Make sure to close the handler to flush all error reporting in progress
}
```


## Development

When all coding and testing is done, please run the test suite:

``` bash
$ make check
```


### Running integration tests

In order to run integration tests, a local development environment must be configured.
Unfortunately it's a little bit more complicated than a "fire and forget" command,
but most of it can be done in the CLI.

The first part is as easy as executing a series of commands:

```bash
cp docker-compose.override.yml.dist docker-compose.override.yml
cp .env.test.dist .env.test
docker-compose up -d
docker-compose run --rm sentry upgrade --noinput
docker-compose run --rm sentry createuser --email admin@example.com --password admin --superuser --no-input
```

Go to the Sentry dashboard:

```bash
open http://localhost:32622
```

Login with `admin@example.com` and `admin` credentials.

Complete the setup wizard and add a new test Go project.

Run the test suite:

```bash
source .env.test
make test
```

Cleanup the environment:

```bash
docker-compose down
```


## License

The MIT License (MIT). Please see [License File](LICENSE) for more information.
