# Go from A to Z
A compilation of knowledge about the Go Programming Language

## Table of contents
<!-- vim-markdown-toc GFM -->

* [Books](#books)
* [Software engineering](#software-engineering)
	- [Design patterns](#design-patterns)
* [Data structures](#data-structures)
* [Semantics](#semantics)
* [HTTP Servers](#http-servers)
* [Error handling](#error-handling)
* [Tooling](#tooling)
	- [Build](#build)
	- [Testing](#testing)
	- [Documentation](#documentation)
	- [Modules](#modules)
* [Databases](#databases)
* [Concurrency](#concurrency)
	- [Channels](#channels)
	- [Contexts](#contexts)
	- [Go runtime scheduler](#go-runtime-scheduler)
	- [Data races](#data-races)
* [Containers](#containers)
* [Background processes ("daemons")](#background-processes-daemons)
* [Misc (unclassified or difficult to classify)](#misc-unclassified-or-difficult-to-classify)

<!-- vim-markdown-toc -->

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
* [Use internal packages to reduce your public API surface](https://dave.cheney.net/2019/10/06/use-internal-packages-to-reduce-your-public-api-surface): A brief intro into a correct taxonomy of a project's folders and subfolders, specially the meaning of the internal packages subfolder. [_Dave Cheney_]
* [Five suggestions for setting up a Go project](https://dave.cheney.net/2014/12/01/five-suggestions-for-setting-up-a-go-project): An intro into the logic behind packages' names, directory structure in a project. A good article to know how to setup a project before actually starting to work on it. [_Dave Cheney_]
* [Why you shouldn't use func main() in Go](https://pace.dev/blog/2020/02/12/why-you-shouldnt-use-func-main-in-golang-by-mat-ryer.html): An article explaining that calling a function `run()` inside main, and passing `os.Args` and `std.out`, etc to it, is more testable than just using main(). [_Mat Ryer_]

## Data structures
* [Go Data Structures](https://research.swtch.com/godata): A description of the memory implementation of some basic types in Go: bytes, int, floats, structs, pointers, strings and slices. Furthermore, a description of the functions for data structure creation `make` and `new`. [_Russ Cox_]

## Semantics
* [The Go Programming Language Specification](https://go.dev/ref/spec): Official language specification
* [Golang Interfaces Explained](https://www.alexedwards.net/blog/interfaces-explained): Definition, meaning and usefulness of interfaces. [_Alex Edwards_]
* [Why Infer Types?](https://npf.io/2022/05/why-infer/): The reasoning behind infering types instead of explicit type definitions. [_Nate Finch_]

## HTTP Servers
* [Validation Snippets for Go](https://www.alexedwards.net/blog/validation-snippets-for-go): Common validation patterns for data being sent to a server through a POST request [_Alex Edwards_]
* [A Guide To Writing Logging Middleware in Go](https://blog.questionable.services/article/guide-logging-middleware-go/): Step by step guide to write logging middleware. [_Matt Silverlock_]
* [Which Go router should I use?](https://www.alexedwards.net/blog/which-go-router-should-i-use): Comparison and evaluation of popular router options for Go. [_Alex Edwards_]
* [Hot to Rate Limit HTTP requests](https://www.alexedwards.net/blog/how-to-rate-limit-http-requests): Excellent article about how to properly set a maximum rate of requests in a given time from a particular user. [_Alex Edwards_]

## Error handling
* [Why Go error handling is awesome](https://rauljordan.com/2020/07/06/why-go-error-handling-is-awesome.html): A discussion and comparison of error handling in Go with other languages. A good explanation about giving context to errors with `fmt.Errorf()`. [_Raul Jordan_]
* [Error handling guidelines for Go](https://jayconrod.com/posts/116/error-handling-guidelines-for-go): The logic behind properly handling errors, be it with the error interface or by returning sentinel values. [_Jay Conrod_]
* [Go (Golang) - Errors and panics](https://unixsheikh.com/articles/go-errors-and-panics.html): An argument for verbosity in error handling in Go [_Unix Sheikh_]

## Tooling
* [An overview of Go's Tooling](https://www.alexedwards.net/blog/an-overview-of-go-tooling): A general overview of the multiple options of the `go` command. [_Alex Edwards_]

### Build
* [Export data, the secret of Go's fast builds](https://jayconrod.com/posts/112/export-data--the-secret-of-go-s-fast-builds): A brief overview about export data in the build process, and how Go tries to speed up the build process. [_Jay Conrod_]
* [Installation with Go Language can be simpler](https://gokcehan.github.io/posts/installation-with-go-language-can-be-simpler.html): Some useful recommendations regarding static linking through use of _CGO_ENABLED_ env variable, stripping binaries at compilation, version in binaries, cross-compilation, etc.
* [Customizing Go binaries with build tags](https://www.digitalocean.com/community/tutorials/customizing-go-binaries-with-build-tags): Tutorial on how to use build tags for cross-compilation. [_DigitalOcean's Go series_]

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
* [Writing a One-to-Many Event Feed Library in Go](https://rauljordan.com/2019/09/23/how-to-write-an-event-feed-library.html): An introduction with example code on how to handle the Pub/Sub design pattern with channels in Go, to basically multicast information to many clients in a concurrent-safe way. [_Raul Jordan_]

### Channels
* [Is it ok to leave a channel open?](https://stackoverflow.com/questions/8593645/is-it-ok-to-leave-a-channel-open): StackOverflow discussion with great sources about the reasoning for not always closing channels. [_StackOverflow_] 

### Contexts
* [How to use contexts in Go](https://www.digitalocean.com/community/tutorials/how-to-use-contexts-in-go): Semantic and syntactic explanation on how to implement contexts in concurrent programs. [_DigitalOcean's Go series_]

### Go runtime scheduler
* [The Go scheduler](https://morsmachine.dk/go-scheduler): High-level description of the interplay of OS threads, goroutines and contexts. How blocking syscalls are handled. [_Daniel Morsing_]
* [The Go netpoller](https://morsmachine.dk/netpoller): How polling primitives of the underline OS are used by Go in order to not block every single thread with a blocking syscall while doing networking. [_Daniel Morsing_]
* [Go's work-stealing scheduler](https://rakyll.org/scheduler/): Description of how the work-stealing algorithm of the Go runtime works [_rakyll_]
* [The Go runtime scheduler's clever way of dealing with system calls](https://utcc.utoronto.ca/~cks/space/blog/programming/GoSchedulerAndSyscalls): More in-detail description of how syscalls are characterized into good and bad syscalls, and the good syscalls are wait upon by the sysmon goroutine [_Chris Siebenmann_}

### Data races
* [Data race patterns in Go](https://eng.uber.com/data-race-patterns-in-go/) [A study of real-world data races in Golang](https://arxiv.org/pdf/2204.00764.pdf): An article by a dev team at Uber, in which they talk about the data race patterns that they found by scanning the vast Go codebase at Uber (also published as a peer-reviewed article).
* [Ice cream makers and data races](https://dave.cheney.net/2014/06/27/ice-cream-makers-and-data-races): A demonstration and explanation of data races taking place with interfaces in part due to the memory model of interfaces. [_Dave Cheney_]
* [Are Go maps sensitive to data races?](https://dave.cheney.net/2015/12/07/are-go-maps-sensitive-to-data-races): An explanation of why maps are more susceptible to causing data races and problems in concurrent applications, than other more simple data structures (as slices). [_Dave Cheney_]

## Containers
* [Using GoLang with Docker](https://golangdocs.com/golang-docker): Step by step guide to run a Go app in a Docker container, with example Dockerfile.
* [Building Docker Images for Static Go Binaries](https://medium.com/@kelseyhightower/optimizing-docker-images-for-static-binaries-b5696e26eb07#.r4j4suwn2): Creating a very small size Docker image for a static Go binary. [_Kelsey Hightower_]

## Background processes ("daemons")
* [Supervised FreeBSD rc.d script for a Go daemon](https://redbyte.eu/en/blog/supervised-freebsd-init-script-for-go-deamon/): Run a go program as a supervised daemon in FreeBSD.
* [Write and auto-deploy daemons in FreeBSD](https://dev.to/zilti/updated-write-and-auto-deploy-daemons-on-freebsd-k7i): How to write and auto-deploy daemons using the `daemon(8)` FreeBSD functionality and rc.
* [Four Steps to Daemonize Your Go Programs](https://ieftimov.com/post/four-steps-daemonize-your-golang-programs/): How to correctly setup a daemon in Go, handle signals SIGTERM, SIGHUP, logging, etc. [_Ilija Eftimov_]
* [runtime: support for daemonize #227](https://github.com/golang/go/issues/227): GitHub thread regarding the difficulties of running a Go program as a usual Unix daemon
* [Running Go Applications in the Background](https://blog.questionable.services/article/running-go-applications-in-the-background/): Using _Supervisor_ to run a Go program in the background, handle logging, email notifications and restarts if the program crashes. [_Matt Silverlock_]

## Misc (unclassified or difficult to classify)
* [Reading list for a training](https://github.com/ardanlabs/gotraining/tree/master/reading): Reading list has a lot of further interesting links
