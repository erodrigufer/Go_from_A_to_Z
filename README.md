# Go from A to Z
A compilation of knowledge about the Go Programming Language

## Books
* [The Go Programming Language](https://www.gopl.io): The Bible. [_Alan A. A. Donovan and Brian W. Kernighan_]
* [Network Programming with Go](https://nostarch.com/networkprogrammingwithgo) (No Starch Press): In depth analysis of how to properly handle http servers, TCP/UDP connections, client and server timeouts, networking error handling, telemetry, etc. [_Adam Woodbeck_]
* [Let's go](https://lets-go.alexedwards.net/): Hands-on/practical book to build Web applications in Go. [_Alex Edwards_]
* [Let's go further](https://lets-go-further.alexedwards.net/): Advanced patterns for building APIs and web applications in Go. Metrics, Authentication, JSON responses, DB operations, etc. [_Alex Edwards_]
* [Concurrency in Go](https://www.oreilly.com/library/view/concurrency-in-go/9781491941294/) (O'Reilly) [_Katherine Cox-Buday_]

## Software engineering
### Design patterns
* [A theory of modern Go](https://peter.bourgon.org/blog/2017/06/09/theory-of-modern-go.html): Reasoning behind avoiding global state and init() functions, and instead use dependecy injections and/or interfaces. [_Peter Bourgon_]
* [Go best practices, six years in](https://peter.bourgon.org/go-best-practices-2016/): Best practices summed up in a long article. Everything from handling dependencies, to repository layout, testing, logging, etc. [_Peter Bourgon_]
* [Go for Industrial programming](https://peter.bourgon.org/go-for-industrial-programming/): Another great article with best practices around: adequately handling concurrency and goroutine's creation and definition (properly handling the interruption of a goroutine), observability (metrics, logging, tracing), dependencies, testing, etc. [_Peter Bourgon_]
* [Go (Golang) - understanding the object oriented features with structs, methods, and interfaces](https://unixsheikh.com/articles/go-understanding-the-object-oriented-features-with-structs-methods-and-interfaces.html): How Go implements OOP paradigma in a different more effective way. [_Unix Sheikh_]

## Data structures
* [Go Data Structures](https://research.swtch.com/godata): A description of the memory implementation of some basic types in Go: bytes, int, floats, structs, pointers, strings and slices. Furthermore, a description of the functions for data structure creation `make` and `new`. [_Russ Cox_]

## Semantics
* [The Go Programming Language Specification](https://go.dev/ref/spec): Official language specification
* [Golang Interfaces Explained](https://www.alexedwards.net/blog/interfaces-explained): Definition, meaning and usefulness of interfaces. [_Alex Edwards_]

## HTTP Servers
* [Validation Snippets for Go](https://www.alexedwards.net/blog/validation-snippets-for-go): Common validation patterns for data being sent to a server through a POST request [_Alex Edwards_]
* [A Guide To Writing Logging Middleware in Go](https://blog.questionable.services/article/guide-logging-middleware-go/): Step by step guide to write logging middleware. [_Matt Silverlock_]
* [Which Go router should I use?](https://www.alexedwards.net/blog/which-go-router-should-i-use): Comparison and evaluation of popular router options for Go. [_Alex Edwards_]
* [Hot to Rate Limit HTTP requests](https://www.alexedwards.net/blog/how-to-rate-limit-http-requests): Excellent article about how to properly set a maximum rate of requests in a given time from a particular user. [_Alex Edwards_]

## Error handling
* [Error handling guidelines for Go](https://jayconrod.com/posts/116/error-handling-guidelines-for-go): The logic behind properly handling errors, be it with the error interface or by returning sentinel values. [_Jay Conrod_]
* [Go (Golang) - Errors and panics](https://unixsheikh.com/articles/go-errors-and-panics.html): An argument for verbosity in error handling in Go [_Unix Sheikh_]

## Tooling
* [An overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling): A general overview of the multiple options of the `go` command.

### Build
* [Export data, the secret of Go's fast builds](https://jayconrod.com/posts/112/export-data--the-secret-of-go-s-fast-builds): A brief overview about export data in the build process, and how Go tries to speed up the build process. [_Jay Conrod_]
* [Installation with Go Language can be simpler](https://gokcehan.github.io/posts/installation-with-go-language-can-be-simpler.html): Some useful recommendations regarding static linking through use of _CGO_ENABLED_ env variable, stripping binaries at compilation, version in binaries, cross-compilation, etc.
* [Customizing Go binaries with build tags](https://www.digitalocean.com/community/tutorials/customizing-go-binaries-with-build-tags): Tutorial on how to use build tags for cross-compilation.

### Testing
* [Testing in Go: go test](https://ieftimov.com/post/testing-in-go-go-test/): In depth description to start configuring a project for testing: test coverage, flags and options of go test, test result caching, etc.  [_Ilija Eftimov_]

### Documentation
* [Testable Examples in Go](https://go.dev/blog/examples): Official documentation on how to integrate example code to the documentation.

### Modules
* [Life of a Go module](https://jayconrod.com/posts/118/life-of-a-go-module): How GOPROXY, checksum and in general the module handling system works. [_Jay Conrod_]

## Databases
* [Go database/sql tutorial](http://go-database-sql.org/index.html)
* [Organising database access in Go](https://www.alexedwards.net/blog/organising-database-access): Choosing between handling database connection pools with global variables, own types and dependency injection through methods and context resources. [_Alex Edwards_]
* [GORM: Golang ORM Package](https://golangdocs.com/gorm-golang-orm-package): How to use and setup an Object Relational Mapper in Go to facilitate writing SQL queries.
* [Configuring sql.DB for better performance](https://www.alexedwards.net/blog/configuring-sqldb): Configuring maximum values for open and idle connections to a db, and setting a connection timeout. [_Alex Edwards_]

## Concurrency
* [Learning Go’s Concurrency through illustrations](https://medium.com/@trevor4e/learning-gos-concurrency-through-illustrations-8c4aff603b3): Very basic guide about goroutines and channels with many illustrations. Blocking and non-blocking channels. [_Trevor Forrey_]

### Go runtime scheduler
* [The Go scheduler](https://morsmachine.dk/go-scheduler): High-level description of the interplay of OS threads, goroutines and contexts. How blocking syscalls are handled. [_Daniel Morsing_]
* [The Go netpoller](https://morsmachine.dk/netpoller): How polling primitives of the underline OS are used by Go in order to not block every single thread with a blocking syscall while doing networking. [_Daniel Morsing_]
* [Go's work-stealing scheduler](https://rakyll.org/scheduler/): Description of how the work-stealing algorithm of the Go runtime works [_rakyll_]
* [The Go runtime scheduler's clever way of dealing with system calls](https://utcc.utoronto.ca/~cks/space/blog/programming/GoSchedulerAndSyscalls): More in-detail description of how syscalls are characterized into good and bad syscalls, and the good syscalls are wait upon by the sysmon goroutine [_Chris Siebenmann_}

## Containers
* [Using GoLang with Docker](https://golangdocs.com/golang-docker): Step by step guide to run a Go app in a Docker container, with example Dockerfile.
* [Building Docker Images for Static Go Binaries](https://medium.com/@kelseyhightower/optimizing-docker-images-for-static-binaries-b5696e26eb07#.r4j4suwn2): Creating a very small size Docker image for a static Go binary. [_Kelsey Hightower_]

## Background processes ("daemons")
* [Four Steps to Daemonize Your Go Programs](https://ieftimov.com/post/four-steps-daemonize-your-golang-programs/): How to correctly setup a daemon in Go, handle signals SIGTERM, SIGHUP, logging, etc. [_Ilija Eftimov_]
* [runtime: support for daemonize #227](https://github.com/golang/go/issues/227): GitHub thread regarding the difficulties of running a Go program as a usual Unix daemon
* [Running Go Applications in the Background](https://blog.questionable.services/article/running-go-applications-in-the-background/): Using _Supervisor_ to run a Go program in the background, handle logging, email notifications and restarts if the program crashes. [_Matt Silverlock_]

## Misc (unclassified or difficult to classify)
* [Reading list for a training](https://github.com/ardanlabs/gotraining/tree/master/reading): Reading list has a lot of further interesting links
