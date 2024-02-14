# Go from A to Z

A compilation of knowledge about the Go Programming Language

## Table of contents

<!-- vim-markdown-toc GFM -->

- [Official documentation](#official-documentation)
- [Books](#books)
- [Software engineering](#software-engineering)
  - [Design patterns](#design-patterns)
- [Data structures](#data-structures)
- [Semantics](#semantics)
  - [Composition](#composition)
  - [Analysis](#analysis)
- [Web development](#web-development)
  - [HTTP Servers](#http-servers)
  - [TLS](#tls)
  - [Proxy servers](#proxy-servers)
  - [Authentication](#authentication)
- [Monitoring](#monitoring)
- [REST API](#rest-api)
- [Error handling](#error-handling)
- [SSH](#ssh)
- [Tooling](#tooling)
  - [Build](#build)
  - [Testing](#testing)
  - [Documentation](#documentation)
  - [Modules](#modules)
- [Databases](#databases)
- [Concurrency](#concurrency)
  - [Channels](#channels)
  - [Contexts](#contexts)
  - [Go runtime scheduler](#go-runtime-scheduler)
  - [Data races](#data-races)
- [Containers](#containers)
- [Background processes ("daemons")](#background-processes-daemons)
- [Misc (unclassified or difficult to classify)](#misc-unclassified-or-difficult-to-classify)

<!-- vim-markdown-toc -->

## Official documentation

- [Language specification](https://tip.golang.org/ref/spec)
- [Effective Go](https://go.dev/doc/effective_go)

## Books

- [The Go Programming Language](https://www.gopl.io): The Bible. [_Alan A. A. Donovan and Brian W. Kernighan_]
- [Network Programming with Go](https://nostarch.com/networkprogrammingwithgo) (No Starch Press): In depth analysis of how to properly handle http servers, TCP/UDP connections, client and server timeouts, networking error handling, telemetry, etc. [_Adam Woodbeck_]
- [Let's go](https://lets-go.alexedwards.net/): Hands-on/practical book to build Web applications in Go. [_Alex Edwards_]
- [Let's go further](https://lets-go-further.alexedwards.net/): Advanced patterns for building APIs and web applications in Go. Metrics, Authentication, JSON responses, DB operations, etc. [_Alex Edwards_]
- [Concurrency in Go](https://www.oreilly.com/library/view/concurrency-in-go/9781491941294/) (O'Reilly) [_Katherine Cox-Buday_]

## Software engineering

### Design patterns

- [A theory of modern Go](https://peter.bourgon.org/blog/2017/06/09/theory-of-modern-go.html): Reasoning behind avoiding global state and init() functions, and instead use dependecy injections and/or interfaces. [_Peter Bourgon_]
- [Go best practices, six years in](https://peter.bourgon.org/go-best-practices-2016/): Best practices summed up in a long article. Everything from handling dependencies, to repository layout, testing, logging, etc. [_Peter Bourgon_]
- [Go for Industrial programming](https://peter.bourgon.org/go-for-industrial-programming/): Another great article with best practices around: adequately handling concurrency and goroutine's creation and definition (properly handling the interruption of a goroutine), observability (metrics, logging, tracing), dependencies, testing, etc. [_Peter Bourgon_]
- [Go (Golang) - understanding the object oriented features with structs, methods, and interfaces](https://unixsheikh.com/articles/go-understanding-the-object-oriented-features-with-structs-methods-and-interfaces.html): How Go implements OOP paradigma in a different and more effective way. [_Unix Sheikh_]
- [Use internal packages to reduce your public API surface](https://dave.cheney.net/2019/10/06/use-internal-packages-to-reduce-your-public-api-surface): A brief intro into a correct taxonomy of a project's folders and subfolders, specially the meaning of the internal packages subfolder. [_Dave Cheney_]
- [Five suggestions for setting up a Go project](https://dave.cheney.net/2014/12/01/five-suggestions-for-setting-up-a-go-project): An intro into the logic behind packages' names, directory structure in a project. A good article to know how to setup a project before actually starting to work on it. [_Dave Cheney_]
- [Simple Go project layout with modules](https://eli.thegreenplace.net/2019/simple-go-project-layout-with-modules/): The best article I have encountered that explains how to layout a Go project for client consumption as both a library and/or as an executable. [_Eli Bendersky_]
- [Why you shouldn't use func main() in Go](https://pace.dev/blog/2020/02/12/why-you-shouldnt-use-func-main-in-golang-by-mat-ryer.html): An article explaining that calling a function `run()` inside main, and passing `os.Args` and `std.out`, etc to it, is more testable than just using main(). [_Mat Ryer_]
- [We already have Go 2](https://xeiaso.net/blog/we-have-go-2): A tour of general changes in the Go ecosystem (GOPATH, modules, etc.) since its inception.
- [Interface segregation in action with Go](https://gianarb.it/blog/interface-segreation-in-action-with-go): A simple explanatory guide on how to properly use and compose interfaces and the benefits of structuring a program in such a way.
- [Interfaces are not meant for that](https://preslav.me/2023/12/15/golang-interfaces-are-not-meant-for-that/#the-top): [_Preslav Rachev_]
- [Functional Options Pattern in Golang](https://michalzalecki.com/golang-options-pattern/): An explanatory article on how to use the _functional options pattern_ to provide options or initialize fields in a struct with a constructor, instead of passing the field values as parameters. This design pattern is supported in other articles by Dave Cheney. [_Michael Zalecki_]

## Data structures

- [Go Data Structures](https://research.swtch.com/godata): A description of the memory implementation of some basic types in Go: bytes, int, floats, structs, pointers, strings and slices. Furthermore, a description of the functions for data structure creation `make` and `new`. [_Russ Cox_]
- [Maps and memory leaks in Go](https://teivah.medium.com/maps-and-memory-leaks-in-go-a85ebe6e7e69): An article explaining the fact that maps can only grow (even after garbage collection) and how they can potentially increase the memory consumption of a program to dangerous levels. [_Teiva Harsanyi_]

## Semantics

- [The Go Programming Language Specification](https://go.dev/ref/spec): Official language specification
- [Golang Interfaces Explained](https://www.alexedwards.net/blog/interfaces-explained): Definition, meaning and usefulness of interfaces. [_Alex Edwards_]
- [Why Infer Types?](https://npf.io/2022/05/why-infer/): The reasoning behind infering types instead of explicit type definitions. [_Nate Finch_]
- [How to use variadic functions in Go](https://www.digitalocean.com/community/tutorials/how-to-use-variadic-functions-in-go): A DigitalOcean's guide on using variadic functions. [_DigitalOcean_]
- [Implementing enumerations in Golang](https://www.ardanlabs.com/blog/2023/09/implementing-enumerations-in-golang.html): A guide showing a way to implement enumerations and the reasoning behind this specific implementation. [_William Kennedy_]

### Composition

- [Embedding in Go part 1: Structs in structs](https://eli.thegreenplace.net/2020/embedding-in-go-part-1-structs-in-structs/): Part 1 of a 3 part series which focuses on teaching the reasoning behind different compositional patterns with _structs_ and _interfaces_. [_Eli Bendersky_]
- [Embedding in Go part 2: Interfaces in interfaces](https://eli.thegreenplace.net/2020/embedding-in-go-part-2-interfaces-in-interfaces/): Part 2 of a 3 part series which focuses on teaching the reasoning behind different compositional patterns with _structs_ and _interfaces_. [_Eli Bendersky_]
- [Embedding in Go part 3: Interfaces in structs](https://eli.thegreenplace.net/2020/embedding-in-go-part-3-interfaces-in-structs/): Part 3 of a 3 part series which focuses on teaching the reasoning behind different compositional patterns with _structs_ and _interfaces_. [_Eli Bendersky_]

### Analysis

- [The ultime guide to writing a Go tool](https://arslan.io/2017/09/14/the-ultimate-guide-to-writing-a-go-tool/): A guide on how to use semantic/language analysis tools from the standard library to write a Go tool. [_Fatih Arslan_]

## Web development

### HTTP Servers

- [How I write HTTP services in Go after 13 years](https://grafana.com/blog/2024/02/09/how-i-write-http-services-in-go-after-13-years/): Great read with some more advanced insights into how to structure and develop a backend web service. [_Mat Ryer_]
- [Validation Snippets for Go](https://www.alexedwards.net/blog/validation-snippets-for-go): Common validation patterns for data being sent to a server through a POST request [_Alex Edwards_]
- [A Guide To Writing Logging Middleware in Go](https://blog.questionable.services/article/guide-logging-middleware-go/): Step by step guide to write logging middleware. [_Matt Silverlock_]
- [Which Go router should I use?](https://www.alexedwards.net/blog/which-go-router-should-i-use): Comparison and evaluation of popular router options for Go. [_Alex Edwards_]
- [Hot to Rate Limit HTTP requests](https://www.alexedwards.net/blog/how-to-rate-limit-http-requests): Excellent article about how to properly set a maximum rate of requests in a given time from a particular user. [_Alex Edwards_]
- [Serving static files and web apps in Go](https://eli.thegreenplace.net/2022/serving-static-files-and-web-apps-in-go/): An introduction into using the standard library built-in functionality to create static file servers. The guide also explains how to integrate the static file servers with servers handling dynamic requests. [_Eli Bendersky_]

### TLS

- [Go HTTP servers with TLS](https://eli.thegreenplace.net/2021/go-https-servers-with-tls/): A guide on how to configure TLS authentication for both servers and clients. It is very understandable, easy to follow and provides extra resources and a detail description on how to create self-signed certificates for a testing environment. [_Eli Bendersky_]

### Proxy servers

- [Go and Proxy servers (HTTP proxies)](https://eli.thegreenplace.net/2022/go-and-proxy-servers-part-1-http-proxies/): A guide on how to develop reverse- and forward proxies with Go. [_Eli Bendersky_]

### Authentication

- [Sign in with GitHub in Go](https://eli.thegreenplace.net/2023/sign-in-with-github-in-go/): Using OAuth and GitHub as an identity provider. [_Eli Bendersky_]

## Monitoring

- [Collecting Prometheus metrics in Golang](https://gabrieltanner.org/blog/collecting-prometheus-metrics-in-golang/): A very detailed guide about collecting metrics with Go using Prometheus and finally displaying them in a dashboard with Grafana. [_Gabriel Tanner_]
- [Getting response status code with middleware](https://stackoverflow.com/questions/53272536/how-do-i-get-response-statuscode-in-golang-middleware): A StackOverflow thread on how to capture the _status code_ of a response that has already been sent to a client with the help of the `negroni` library. [_StackOverflow_]
  - [ResponseWriter in negroni](https://github.com/urfave/negroni/blob/master/response_writer.go): `negroni`'s implementation of a `ResponseWriter`, which has additional very useful methods missing in the standard library.

## REST API

- [REST servers in Go part 4: Using OpenAPI and Swagger](https://eli.thegreenplace.net/2021/rest-servers-in-go-part-4-using-openapi-and-swagger/): A guide on how to generate both documentation and an opinionated API server and/or client from a Swagger definition. [_Eli Bendersky_]

## Error handling

- [Why Go error handling is awesome](https://rauljordan.com/2020/07/06/why-go-error-handling-is-awesome.html): A discussion and comparison of error handling in Go with other languages. A good explanation about giving context to errors with `fmt.Errorf()`. [_Raul Jordan_]
- [Error handling guidelines for Go](https://jayconrod.com/posts/116/error-handling-guidelines-for-go): The logic behind properly handling errors, be it with the error interface or by returning sentinel values. [_Jay Conrod_]
- [Go (Golang) - Errors and panics](https://unixsheikh.com/articles/go-errors-and-panics.html): An argument for verbosity in error handling in Go [_Unix Sheikh_]

## SSH

- [SSH port forwarding with Go](https://eli.thegreenplace.net/2022/ssh-port-forwarding-with-go/): A guide on how to create an SSH tunnel with Go. [_Eli Bendersky_]

## Tooling

- [An overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling): A general overview of the multiple options of the `go` command. [_Alex Edwards_]

### Build

- [Export data, the secret of Go's fast builds](https://jayconrod.com/posts/112/export-data--the-secret-of-go-s-fast-builds): A brief overview about export data in the build process, and how Go tries to speed up the build process. [_Jay Conrod_]
- [Installation with Go Language can be simpler](https://gokcehan.github.io/posts/installation-with-go-language-can-be-simpler.html): Some useful recommendations regarding static linking through use of _CGO_ENABLED_ env variable, stripping binaries at compilation, version in binaries, cross-compilation, etc.
- [Customizing Go binaries with build tags](https://www.digitalocean.com/community/tutorials/customizing-go-binaries-with-build-tags): Tutorial on how to use build tags for cross-compilation. [_DigitalOcean's Go series_]
- [3 ways to embed commit hash to Go programs](https://developers.redhat.com/articles/2022/11/14/3-ways-embed-commit-hash-go-programs): A guide on how to embed a commit hash to a Go program at build time. [_Red Hat_]

### Testing

- [Testing in Go: go test](https://ieftimov.com/post/testing-in-go-go-test/): In depth description to start configuring a project for testing: test coverage, flags and options of go test, test result caching, etc. [_Ilija Eftimov_]
- [Don't use a different interface for testing](https://www.komu.engineer/blogs/10/dont-use-a-different-interface-for-testing): A good explanatory article explaining why not using the same interface for testing is not a good idea due to code coverage.
- [Testing a CLI command with cobra](https://gianarb.it/blog/golang-mockmania-cli-command-with-cobra): An explanation on to how to test a CLI implemented with cobra.

### Documentation

- [Testable Examples in Go](https://go.dev/blog/examples): Official documentation on how to integrate example code to the documentation.

### Modules

- [Life of a Go module](https://jayconrod.com/posts/118/life-of-a-go-module): How GOPROXY, checksum and in general the module handling system works. [_Jay Conrod_]

## Databases

- [Go database/sql tutorial](http://go-database-sql.org/index.html)
- [Organising database access in Go](https://www.alexedwards.net/blog/organising-database-access): Choosing between handling database connection pools with global variables, own types and dependency injection through methods and context resources. [_Alex Edwards_]
- [GORM: Golang ORM Package](https://golangdocs.com/gorm-golang-orm-package): How to use and setup an Object Relational Mapper in Go to facilitate writing SQL queries.
- [Configuring sql.DB for better performance](https://www.alexedwards.net/blog/configuring-sqldb): Configuring maximum values for open and idle connections to a db, and setting a connection timeout. [_Alex Edwards_]

## Concurrency

- [Learning Go’s Concurrency through illustrations](https://medium.com/@trevor4e/learning-gos-concurrency-through-illustrations-8c4aff603b3): Very basic guide about goroutines and channels with many illustrations. Blocking and non-blocking channels. [_Trevor Forrey_]
- [Writing a One-to-Many Event Feed Library in Go](https://rauljordan.com/2019/09/23/how-to-write-an-event-feed-library.html): An introduction with example code on how to handle the Pub/Sub design pattern with channels in Go, to basically multicast information to many clients in a concurrent-safe way. [_Raul Jordan_]

### Channels

- [Is it ok to leave a channel open?](https://stackoverflow.com/questions/8593645/is-it-ok-to-leave-a-channel-open): StackOverflow discussion with great sources about the reasoning for not always closing channels. [_StackOverflow_]

### Contexts

- [How to use contexts in Go](https://www.digitalocean.com/community/tutorials/how-to-use-contexts-in-go): Semantic and syntactic explanation on how to implement contexts in concurrent programs. [_DigitalOcean's Go series_]

### Go runtime scheduler

- [The Go scheduler](https://morsmachine.dk/go-scheduler): High-level description of the interplay of OS threads, goroutines and contexts. How blocking syscalls are handled. [_Daniel Morsing_]
- [The Go netpoller](https://morsmachine.dk/netpoller): How polling primitives of the underline OS are used by Go in order to not block every single thread with a blocking syscall while doing networking. [_Daniel Morsing_]
- [Go's work-stealing scheduler](https://rakyll.org/scheduler/): Description of how the work-stealing algorithm of the Go runtime works [_rakyll_]
- [The Go runtime scheduler's clever way of dealing with system calls](https://utcc.utoronto.ca/~cks/space/blog/programming/GoSchedulerAndSyscalls): More in-detail description of how syscalls are characterized into good and bad syscalls, and the good syscalls are wait upon by the sysmon goroutine [_Chris Siebenmann_]

### Data races

- [Data race patterns in Go](https://eng.uber.com/data-race-patterns-in-go/) [A study of real-world data races in Golang](https://arxiv.org/pdf/2204.00764.pdf): An article by a dev team at Uber, in which they talk about the data race patterns that they found by scanning the vast Go codebase at Uber (also published as a peer-reviewed article).
- [Ice cream makers and data races](https://dave.cheney.net/2014/06/27/ice-cream-makers-and-data-races): A demonstration and explanation of data races taking place with interfaces in part due to the memory model of interfaces. [_Dave Cheney_]
- [Are Go maps sensitive to data races?](https://dave.cheney.net/2015/12/07/are-go-maps-sensitive-to-data-races): An explanation of why maps are more susceptible to causing data races and problems in concurrent applications, than other more simple data structures (as slices). [_Dave Cheney_]

## Containers

- [Using GoLang with Docker](https://golangdocs.com/golang-docker): Step by step guide to run a Go app in a Docker container, with example Dockerfile.
- [Building Docker Images for Static Go Binaries](https://medium.com/@kelseyhightower/optimizing-docker-images-for-static-binaries-b5696e26eb07#.r4j4suwn2): Creating a very small size Docker image for a static Go binary. [_Kelsey Hightower_]

## Background processes ("daemons")

- [Supervised FreeBSD rc.d script for a Go daemon](https://redbyte.eu/en/blog/supervised-freebsd-init-script-for-go-deamon/): Run a go program as a supervised daemon in FreeBSD.
- [Write and auto-deploy daemons in FreeBSD](https://dev.to/zilti/updated-write-and-auto-deploy-daemons-on-freebsd-k7i): How to write and auto-deploy daemons using the `daemon(8)` FreeBSD functionality and rc.
- [Four Steps to Daemonize Your Go Programs](https://ieftimov.com/post/four-steps-daemonize-your-golang-programs/): How to correctly setup a daemon in Go, handle signals SIGTERM, SIGHUP, logging, etc. [_Ilija Eftimov_]
- [runtime: support for daemonize #227](https://github.com/golang/go/issues/227): GitHub thread regarding the difficulties of running a Go program as a usual Unix daemon
- [Running Go Applications in the Background](https://blog.questionable.services/article/running-go-applications-in-the-background/): Using _Supervisor_ to run a Go program in the background, handle logging, email notifications and restarts if the program crashes. [_Matt Silverlock_]

## Misc (unclassified or difficult to classify)

- [Reading list for a training](https://github.com/ardanlabs/gotraining/tree/master/reading): Reading list has a lot of further interesting links
- [Upgrading Go in Ubuntu](https://github.com/golang/go/wiki/Ubuntu)
- [Between Golang and Elixir](https://preslav.me/2021/04/23/between-golang-and-elixir/): A guide of how to integrate Go and Elixir together, and when it makes sense to use them.
