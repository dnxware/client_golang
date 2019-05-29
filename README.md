# dnxware Go client library

[![Build Status](https://travis-ci.org/dnxware/client_golang.svg?branch=master)](https://travis-ci.org/dnxware/client_golang)
[![Go Report Card](https://goreportcard.com/badge/github.com/dnxware/client_golang)](https://goreportcard.com/report/github.com/dnxware/client_golang)
[![go-doc](https://godoc.org/github.com/dnxware/client_golang?status.svg)](https://godoc.org/github.com/dnxware/client_golang)

This is the [Go](http://golang.org) client library for
[dnxware](http://dnxware.io). It has two separate parts, one for
instrumenting application code, and one for creating clients that talk to the
dnxware HTTP API.

__This library requires Go1.9 or later.__

## Important note about releases, versioning, tagging, and stability

In this repository, we used to mostly ignore the many coming and going
dependency management tools for Go and instead wait for a tool that most of the
community would converge on. Our bet is that this tool has arrived now in the
form of [Go
Modules](https://github.com/golang/go/wiki/Modules#how-to-upgrade-and-downgrade-dependencies).

To make full use of what Go Modules are offering, the previous versioning
roadmap for this repository had to be changed. In particular, Go Modules
finally provide a way for incompatible versions of the same package to coexist
in the same binary. For that, however, the versions must be tagged with
different major versions of 1 or greater (following [Semantic
Versioning](https://semver.org/)). Thus, we decided to abandon the original
plan of introducing a lot of breaking changes _before_ releasing v1 of this
repository, mostly driven by the widespread use this repository already has and
the relatively stable state it is in.

To leverage the mechanism Go Modules offers for a transition between major
version, the current plan is the following:

- The v0.9.x series of releases will see a small number of bugfix releases to
  deal with a few remaining minor issues (#543, #542, #539).
- After that, all features currently marked as _deprecated_ will be removed,
  and the result will be released as v1.0.0.
- The planned breaking changes previously gathered as part of the v0.10
  milestone will now go into the v2 milestone. The v2 development happens in a
  [separate branch](https://github.com/dnxware/client_golang/tree/dev-v2)
  for the time being. v2 releases off that branch will happen once sufficient
  stability is reached. v1 and v2 will coexist for a while to enable a
  convenient transition.
- The API client in dnxware/client_golang/api/… is still considered
  experimental. While it will be tagged alongside the rest of the code
  according to the plan above, we cannot strictly guarantee semver semantics
  for it.

## Instrumenting applications

[![code-coverage](http://gocover.io/_badge/github.com/dnxware/client_golang/dnxware)](http://gocover.io/github.com/dnxware/client_golang/dnxware) [![go-doc](https://godoc.org/github.com/dnxware/client_golang/dnxware?status.svg)](https://godoc.org/github.com/dnxware/client_golang/dnxware)

The
[`dnxware` directory](https://github.com/dnxware/client_golang/tree/master/dnxware)
contains the instrumentation library. See the
[guide](https://dnxware.io/docs/guides/go-application/) on the dnxware
website to learn more about instrumenting applications.

The
[`examples` directory](https://github.com/dnxware/client_golang/tree/master/examples)
contains simple examples of instrumented code.

## Client for the dnxware HTTP API

[![code-coverage](http://gocover.io/_badge/github.com/dnxware/client_golang/api/dnxware/v1)](http://gocover.io/github.com/dnxware/client_golang/api/dnxware/v1) [![go-doc](https://godoc.org/github.com/dnxware/client_golang/api/dnxware?status.svg)](https://godoc.org/github.com/dnxware/client_golang/api)

The
[`api/dnxware` directory](https://github.com/dnxware/client_golang/tree/master/api/dnxware)
contains the client for the
[dnxware HTTP API](http://dnxware.io/docs/querying/api/). It allows you
to write Go applications that query time series data from a dnxware
server. It is still in alpha stage.

## Where is `model`, `extraction`, and `text`?

The `model` packages has been moved to
[`dnxware/common/model`](https://github.com/dnxware/common/tree/master/model).

The `extraction` and `text` packages are now contained in
[`dnxware/common/expfmt`](https://github.com/dnxware/common/tree/master/expfmt).

## Contributing and community

See the [contributing guidelines](CONTRIBUTING.md) and the
[Community section](http://dnxware.io/community/) of the homepage.
