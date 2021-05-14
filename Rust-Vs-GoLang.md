# Rust Vs GoLang

> Abstract/Summary from following blogs:
> - https://bitfieldconsulting.com/golang/rust-vs-go
> - https://blog.logrocket.com/when-to-use-rust-and-when-to-use-golang/
> - https://thenewstack.io/rust-vs-go-why-theyre-better-together/
> - https://trio.dev/blog/golang-vs-rust

## Common points
- Open source
- compiled languages:
    - compiled to native machine code, deploy with single binary file.
    - extremely fast in comparison to interpreted languages
- Truly Portable: write one piece of software that runs on many different operating systems and architectures.
- memory safety:
    + Both are good at it but Rust gains a higher edge by a short margine.
    + Rust uses a borrow checker to validate memory safety and not GC.
- Both suited will for parallel computing environments and to optimize the utilization of available CPU cores through concurrency.
- General-purpose languages: Can develop web applications to distributed microservices, or from embedded microcontrollers to mobile apps
- Pragmatic programming style: Functional and object-oriented programming
- Development at scale
    - suitable for programming in the large, whether that means large teams, or large codebases, or both.
    - standard formatting tool (gofmt for Go, rustfmt for Rust) which rewrites your code automatically using the canonical style.
    - build pipeline - Both have excellent, built-in, high-performance standard build and dependency management tools

---

## Comparison points

- **History**
    + Go: Originally designed by Google’s engineers, Go was introduced to the public in 2009. It was created to offer an alternative to C++ that was easier to learn and code and was optimized to run on multicore CPUs.
    + Rust: 2010, Mozilla. Mozilla employees first started experimenting with what would later become Rust in 2006. After a stable release about three years later, Rust is now used in key parts of the Firefox browser.

- **Performance: Rust**
    + Rust will usually beat Go in run-time benchmarks.
    + Rust's performance is particularly outstanding. It's comparable with C and C++, which are often regarded as the highest-performance compiled languages, but unlike these older languages, it also offers memory safety and concurrency safety at essentially no cost in execution speed.
    + Go is primarily designed for speed of development (including compilation), rather than speed of execution.
    + The Go compiler also doesn’t spend a lot of time trying to generate the most efficient possible machine code; it cares more about compiling lots of code quickly.
    + Rust’s run-time performance is also consistent and predictable, because it doesn’t use garbage collection. Go’s garbage collector is very efficient, and it’s optimised but garbage collection inevitably introduces some unpredictability in the way programs behave, which can be a serious issue in some applications.
    + Rust aims to give the programmer complete control of the underlying hardware, it's possible to optimise Rust programs to be pretty close to the maximum theoretical performance of the machine. This makes Rust an excellent choice for areas where speed of execution beats all other considerations, such as game programming, operating system kernels, web browser components, and real-time control systems.

- **Simplicity: Go**
    - Go is also designed for software development at scale, with large codebases and large teams. In these situations, it's important that new developers can get up to speed as quickly as possible. For this reason, the Go community values simple, obvious, conventional, straightforward programs.

- **Features: Rust**
    - Rust is specifically designed to include lots of powerful and useful features to help programmers do the most with the least code.
    - While Rust has adopted some of Go's features, and Go is adopting some of Rust's (notably generics, it's fair to say that Rust is feature-heavy and Go is comparatively feature-light.

- **Concurrency**
    + Rust
        + While Rust has adopted some of Go's features, and Go is adopting some of Rust's (notably generics, it's fair to say that Rust is feature-heavy and Go is comparatively feature-light.
        + Rust's concurrency: https://blog.rust-lang.org/2015/04/10/Fearless-Concurrency.html
        + Rust offers four different concurrency paradigms to help you avoid common memory safety pitfalls (e.g: channel, lock).
        + Rust gives you fine-grained control over how threads behave and how resources are shared between threads.
    + golang:
        + The language provides goroutines that enable you to run functions as subprocesses.
        + Go’s concurrency model allows you to deploy workloads across multiple CPU cores, making it a very efficient language.
        + Go's concurrency support feels well-designed, and a pleasure to use. 
        + Go is focused on concurrency as a first class concept. That is not to say you cannot find aspects of Go’s actor oriented concurrency in Rust, but it is left as an exercise to the programmer.

- **Safety: Rust**
    - Rust in particular goes to great lengths to ensure that you can't do something unsafe that you didn't mean to do.

- **Scale: Go**
    - For large applications and distributed systems, speed of execution is less important than speed of development.
    - Go was designed and developed to make working in this environment more productive. Go's design considerations include rigorous dependency management, the adaptability of software architecture as systems grow, and robustness across the boundaries between components.

- **Garbage collection: Rust**
    - Having GC in Go makes the language much simpler and smaller, and easy to reason about.
    - Not having GC in Rust makes it really fast (especially if you need guaranteed latency, not just high throughput) and enables features and programming patterns that are not possible in Go (or at least not without sacrificing performance).

- **Close to the metal/ Better control over underlying hardware: Rust**
    + Precise Control
    + Rust aims to let programmers get “closer to the metal”, with more control, but Go abstracts away the architectural details to let programmers get closer to the problem.

- **Must run faster: Rust**
    + Rust is faster than Go. In the benchmarks above, Rust was faster, and in some cases, an order of magnitude faster.
    + If what you need is top-of-the-line performance, then you’ll be ahead of the game choosing either of these two languages. If you’re building a web service that handles high load, that you want to be able to scale both vertically and horizontally, either language will suit you perfectly.

- **Community: Rust**
    + Without a doubt, both Rust and Go have strong communities, but Rust’s community gets the most visibility in this Golang vs. Rust stand-off. Simply put, Rust wins. 

- **Learnability - Developer Learning curve: Go**
    + The learning curve for Rust is pretty steep compared to Go.

- **Development time: Go**
    + Go for the code that has to ship tomorrow, Rust for the code that has to keep running untouched for the next five years.
    + If you want to develop faster, perhaps because you have many different services to write, or you have a large team of developers, then Go is your language of choice. Go gives you concurrency as a first-class citizen, and does not tolerate unsafe memory access (neither does Rust), but without forcing you to manage every last detail. Go is fast and powerful, but it avoids bogging the developer down, focusing instead on simplicity and uniformity. If on the other hand, wringing out every last ounce of performance is a necessity, then Rust should be your choice.

- **Development Efforts: Go**
    + Rust, things are much harder from a developer experience point of view.

- **Type of Projects**
    + Go:
        * Has a stronger focus on building web APIs and small services that can scale endlessly, especially with the power of goroutines. 
        * Built-in support for the HTTP web protocol. 
        * Go fits well with the microservices architecture and serves the needs of API developers and good code redability.
    + Rust:
        * Projects that demand high performance.
        * works well for processing large amounts of data and other CPU-intensive operations, such as executing algorithms.

- **When to use which language**
    + Go: APIs, Web Apps, CLI apps, DevOps, Networking, Data Processing, cloud apps
    + Rust: IoT, processing engines, security-sensitive apps, system components, cloud apps

- **Adoption by big organisations**
    + Go: Kubernetes, Docker, Github CLI, Hugo, Caddy, Drone, Ethereum, Syncthing, Terraform, PayPal, ...
    + Rust: AWS, Firefox, ripgrep, alacritty, deno, Habitat, IBM, Discord, Dropbox, Microsoft, cloudflare, Yelp, ...

- **Case studies**
    + https://bitbucket.org/blog/why-rust

- **Benchmarks: Rust**
    + https://benchmarksgame-team.pages.debian.net/benchmarksgame/fastest/rust-go.html

- **Quotes**
    + I think quotes matters, because these are voices of developers whi used and built something which is generating money.
    + Go is simple. Rust is complex. 
    + Go:
        * “At the time, no single team member knew Go, but within a month, everyone was writing in Go” – Jaime Garcia, Capital One
        * “Using Go allowed MercadoLibre to cut the number of servers they use for this service to one-eighth the original number (from 32 servers down to four), plus each server can operate with less power (originally four CPU cores, now down to two CPU cores). With Go, the company obviated 88 percent of their servers and cut CPU on the remaining ones in half—producing a tremendous cost-savings.”— “MercadoLibre Grows with Go”
        * “(I)f your use case is closer to customers, it’s more vulnerable to shifting requirements, then Go is a lot nicer because the cost of continuous refactor is a lot cheaper. It’s how fast you can express the new requirements and try them out.” — Peter Bourgon, Fastly
        * “In our tightly managed environments where we run Go code, we have seen a CPU reduction of approximately ten percent [vs C++] with cleaner and maintainable code.” — Bala Natarajan, Paypal
        * “Go is strongly and statically typed with no implicit conversions, but the syntactic overhead is still surprisingly small. This is achieved by simple type inference in assign­ments together with untyped numeric constants. This gives Go stronger type safety than Java (which has implicit conversions), but the code reads more like Python (which has untyped variables).” — Stefan Nilsson, computer science professor.
        * “Golang possesses great qualities for production optimization such as having a small memory footprint, which supports its capability for being building blocks in large-scale projects, as well as easy cross-compilation to other architectures out of the box. Since Go code is compiled into a single static binary, it allows easy containerization and, by extension, makes it almost trivial to deploy Go into any highly available environment such as Kubernetes.” — Dewet Diener, Curve.
    + Rust:
        * “Here at AWS, we love Rust, too, because it helps AWS write highly performant, safe infrastructure-level networking and other systems software. Amazon’s first notable product built with Rust, Firecracker, launched publicly in 2018 and provides the open source virtualization technology that powers AWS Lambda and other serverless offerings. But we also use Rust to deliver services such as Amazon Simple Storage Service (Amazon S3), Amazon Elastic Compute Cloud (Amazon EC2), Amazon CloudFront, Amazon Route 53, and more. Recently we launched Bottlerocket, a Linux-based container operating system written in Rust.” — Matt Asay, Amazon Web Services
        * We “saw an extraordinary 1200-1500% increase in our speed! We went from 300-450ms in release mode with Scala with fewer parsing rules implemented, to 25-30ms in Rust with more parsing rules implemented!” — Josh Hannaford, IBM
        * “The [Rust] compiler really holds your hand when working through the errors that you do get. This lets you focus on your business objectives rather than bug hunting or deciphering cryptic messages.” — Josh Hannaford, IBM
        * “In short, the flexibility, safety, and security of Rust outweighs any inconvenience of having to follow strict lifetime, borrowing, and other compiler rules or even the lack of a garbage collector. These features are a much-needed addition to cloud software projects and will help avoid many bugs commonly found in them.” — Taylor Thomas, Sr., Microsoft.
        * “When building our Brotli compression library for storing block data at Dropbox, we limited ourselves to the safe subset of Rust and, further, to the core library (no-stdlib) as well, with the allocator specified as a generic. Using the subset of Rust this way made it very easy to call the Rust-Brotli library from Rust on the client-side and using the C FFI from both Python and Go on the Server. This compilation mode also provided substantial security guarantees. After some tuning, the Rust Brotli implementation, despite being 100% safe, array-bounds-checked code, was still faster than the corresponding native Brotli code in C.” — Daniel Reiter Horn, Dropbox
        * “With Rust, we’ll have a high-performance and portable platform that we can easily run on Mac, iOS, Linux, Android, and Windows.” — Matt Ronge, Astropad.
        * “Dropbox engineers often see 5x performance and latency improvements by porting line-for-line Python code into Go, and memory usage often drops dramatically as compared with Python as there is no GIL and the process count may be reduced. However, when we are memory constrained, as on desktop client software or in certain server processes, we move over to Rust as the manual memory management in Rust is substantially more efficient than the Go GC.” — Daniel Reiter Horn, Dropbox
        * “Dropbox engineers often see 5x performance and latency improvements by porting line-for-line Python code into Go, and memory usage often drops dramatically as compared with Python as there is no GIL and the process count may be reduced. However, when we are memory constrained, as on desktop client software or in certain server processes, we move over to Rust as the manual memory management in Rust is substantially more efficient than the Go GC.” — Daniel Reiter Horn, Dropbox
        * “As our experience with Rust grew, it showed advantages on two other axes: as a language with strong memory safety it was a good choice for processing at the edge and as a language that had tremendous enthusiasm it became one that became popular for de novo components.”  — John Graham-Cumming, Cloudflare

- **Misc:**
    + Ranking: https://www.tiobe.com/tiobe-index/
