# Go_from_A_to_Z
A compilation of knowledge about the Go Programming Language

## Books
* [The Go Programming Language](https://www.gopl.io): The Bible. [_Alan A. A. Donovan and Brian W. Kernighan_]
* [Network Programming with Go](https://nostarch.com/networkprogrammingwithgo) (No Starch Press): In depth analysis of how to properly handle http servers, TCP/UDP connections, client and server timeouts, networking error handling, telemetry, etc. [_Adam Woodbeck_]
* [Let's go](https://lets-go.alexedwards.net/): Hands-on/practical book to build Web applications in Go. [_Alex Edwards_]
* [Let's go further](https://lets-go-further.alexedwards.net/): Advanced patterns for building APIs and web applications in Go. Metrics, Authentication, JSON responses, DB operations, etc. [_Alex Edwards_]
* [Concurrency in Go](https://www.oreilly.com/library/view/concurrency-in-go/9781491941294/) (O'Reilly) [_Katherine Cox-Buday_]

## Design patterns
* [A theory of modern Go](https://peter.bourgon.org/blog/2017/06/09/theory-of-modern-go.html): Reasoning behind avoiding global state and init() functions, and instead use dependecy injections and/or interfaces. [_Peter Bourgon_]

## Data structures
* [Go Data Structures](https://research.swtch.com/godata): A description of the memory implementation of some basic types in Go: bytes, int, floats, structs, pointers, strings and slices. Furthermore, a description of the functions for data structure creation `make` and `new`. [_Russ Cox_]

## Semantics
* [Golang Interfaces Explained](https://www.alexedwards.net/blog/interfaces-explained): Definition, meaning and usefulness of interfaces. [_Alex Edwards_]

## HTTP Servers
* [Conditional HTTP GET: The fastest requests need no response body](https://ieftimov.com/post/conditional-http-get-fastest-requests-need-no-response-body/): Handling server content update with ETags and Last-Modified _header fields_ in order to generate user-agent content caching [_Ilija Eftimov_]
* [Validation Snippets for Go](https://www.alexedwards.net/blog/validation-snippets-for-go): Common validation patterns for data being sent to a server through a POST request [_Alex Edwards_]

## Error handling
* [Error handling guidelines for Go](https://jayconrod.com/posts/116/error-handling-guidelines-for-go): The logic behind properly handling errors, be it with the error interface or by returning sentinel values. [_Jay Conrod_]

## Tooling
* [An overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling): A general overview of the multiple options of the `go` command.

### Build
* [Export data, the secret of Go's fast builds](https://jayconrod.com/posts/112/export-data--the-secret-of-go-s-fast-builds): A brief overview about export data in the build process, and how Go tries to speed up the build process. [_Jay Conrod_]

### Testing
* [Testing in Go: go test](https://ieftimov.com/post/testing-in-go-go-test/): In depth description to start configuring a project for testing: test coverage, flags and options of go test, test result caching, etc.  [_Ilija Eftimov_]

### Modules
* [Life of a Go module](https://jayconrod.com/posts/118/life-of-a-go-module): How GOPROXY, checksum and in general the module handling system works. [_Jay Conrod_]

## Databases
* [Go database/sql tutorial](http://go-database-sql.org/index.html)
* [Organising database access in Go](https://www.alexedwards.net/blog/organising-database-access): Choosing between handling databse connection pools with global variables, own types and dependency injection through methods and context resources. [_Alex Edwards_]

## Containers
* [Using GoLang with Docker](https://golangdocs.com/golang-docker): Step by step guide to run a Go app in a Docker container, with example Dockerfile.

## Daemons
* [Four Steps to Daemonize Your Go Programs](https://ieftimov.com/post/four-steps-daemonize-your-golang-programs/): How to correctly setup a daemon in Go, handle signals SIGTERM, SIGHUP, logging, etc. [_Ilija Eftimov_]
