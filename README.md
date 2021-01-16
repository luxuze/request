# Request [![Mentioned in Awesome Go](https://awesome.re/mentioned-badge.svg)](https://github.com/avelino/awesome-go) [![Go Report Card](https://goreportcard.com/badge/github.com/monaco-io/request)](https://goreportcard.com/report/github.com/monaco-io/request) ![Go](https://github.com/monaco-io/request/workflows/Go/badge.svg)

<img align="right" width="159px" src="https://raw.githubusercontent.com/gin-gonic/logo/master/color.png">

[![GoDoc](https://godoc.org/github.com/monaco-io/request?status.svg)](https://pkg.go.dev/github.com/monaco-io/request?tab=doc)
[![codecov](https://codecov.io/gh/monaco-io/request/branch/master/graph/badge.svg)](https://codecov.io/gh/monaco-io/request)
[![Release](https://img.shields.io/github/release/monaco-io/request.svg?style=flat-square)](https://github.com/monaco-io/request/releases)
[![TODOs](https://badgen.net/https/api.tickgit.com/badgen/github.com/monaco-io/request)](https://www.tickgit.com/browse?repo=github.com/monaco-io/request)
[![License](https://img.shields.io/github/license/monaco-io/request?style=plastic)](https://github.com/monaco-io/request/blob/master/LICENSE)
<!-- [![Sourcegraph](https://sourcegraph.com/github.com/monaco-io/request/-/badge.svg)](https://sourcegraph.com/github.com/monaco-io/request?badge) -->
<!-- [![Open Source Helpers](https://www.codetriage.com/monaco-io/request/badges/users.svg)](https://www.codetriage.com/monaco-io/request) -->
<!-- [![Join the chat at https://gitter.im/monaco-io/request](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/monaco-io/request?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) -->

HTTP client for golang, Inspired by [Javascript-axios](https://github.com/axios/axios) [Python-request](https://github.com/psf/requests).
If you have experience about axios or requests, you will love it.
No 3rd dependency.

## Features

- Make [http](https://golang.org) requests from Golang
- Transform request and response data

## Installing

go mod:

```bash
go get github.com/monaco-io/request
```

## Methods

- OPTIONS
- GET
- HEAD
- POST
- PUT
- DELETE
- TRACE
- CONNECT

## Example

### GET

```go
package main

import (
    "log"

    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:    "https://google.com",
        Method: "GET",
        Params: map[string]string{"hello": "world"},
}
```

### POST

```go
package main

import (
    "log"

    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:    "https://google.com",
        Method: "POST",
        Params: map[string]string{"hello": "world"},
        Body:   []byte(`{"hello": "world"}`),
}
```

### Authorization

```go
package main

import (
    "log"

    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:       "https://google.com",
        Method:    "POST",
        BasicAuth: request.BasicAuth{
            Username:"user_xxx",
            Password:"pwd_xxx",
        },
    }
}
```

### Timeout

```go
package main

import (
    "log"
    "time"
    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:       "https://google.com",
        Method:    "POST",
        Timeout:   time.Second*10,
    }
}
```

### Cookies

```go
package main

import (
    "log"

    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:       "https://google.com",
        CookiesMap: map[string]string{
            "cookie_name": "cookie_value",
        }
    }
}
```

### TLS

```go
package main

import (
    "log"
    "crypto/tls"

    "github.com/monaco-io/request"
)

func main() {
    client := request.Client{
        URL:       "https://google.com",
        TLSConfig: &tls.Config{InsecureSkipVerify: true},
    }
}
```

## License

[MIT](LICENSE)
