[![Rust CI/CD Pipeline](https://github.com/noahgift/rdedupe/actions/workflows/rust-hello.yml/badge.svg)](https://github.com/noahgift/rdedupe/actions/workflows/rust-hello.yml)

## RDedupe

A Rust based deduplication tool

### Goals

* Build a multiplatform, fast deduplication tool that uses Rust parallelization.

![Rayon Parallization](https://user-images.githubusercontent.com/58792/209480753-d2452e39-f72b-43c2-8000-b2d9f18d8a33.png)


#### Future Improvements

* Fix GitHub Actions Build process to not fail silently!
* Use Polars DataFrame and include statistics about files and generate a CSV report.
* Store logs about actions performed across multiple runs

### Building and Running

* Build:  cd into rdedupe and run `make all`
* Run:  `cargo run -- dedupe --path tests --pattern .txt`
* Run tests:  `make test`

### OS X Install

* Install rust via [rustup](https://rustup.rs/)
* Add to `~/.cargo/config`

```bash
[target.x86_64-apple-darwin]
rustflags = [
  "-C", "link-arg=-undefined",
  "-C", "link-arg=dynamic_lookup",
]

[target.aarch64-apple-darwin]
rustflags = [
  "-C", "link-arg=-undefined",
  "-C", "link-arg=dynamic_lookup",
]
```
* run `make all` in rdedupe directory
