# Hits-of-Code

[![Hits-of-Code](https://hitsofcode.com/github/vbrandl/hoc)](https://hitsofcode.com/view/github/vbrandl/hoc)
[![Drone build](https://drone.vbrandl.net/api/badges/vbrandl/hoc/status.svg)](https://drone.vbrandl.net/vbrandl/hoc)
[![Gitlab build](https://gitlab.com/vbrandl/hoc/badges/master/pipeline.svg)](https://gitlab.com/vbrandl/hoc/pipelines)
[![Travis build](https://travis-ci.org/vbrandl/hoc.svg?branch=master)](https://travis-ci.org/vbrandl/hoc)
[![dependency status](https://deps.rs/repo/github/vbrandl/hoc/status.svg)](https://deps.rs/repo/github/vbrandl/hoc)

Small webservice, that returns a badge of the Hits-of-Code of a git repository, as described by [Yegor
Bugayenko](https://www.yegor256.com/2014/11/14/hits-of-code.html). It is implemented in
[Rust](https://www.rust-lang.org/), using the [actix-web](https://actix.rs/) web framework.

A live version of this webservice can be found on [hitsofcode.com](https://hitsofcode.com/).

## API

The API is as simple as

```
https://<host>/<service>/<user>/<repo>
```

where `<service>` is one of `gitub`, `gitlab` or `bitbucket`. The HoC data can also be received as JSON by appending
`/json` to the reuqest path:

```
https://<host>/<service>/<user>/<repo>/json
```

There is also an overview page available via `https://<host>/view/<service>/<user>/<repo>`

## Building

The code can be built as a standalone binary, using `cargo` or as a Docker container. Run either

```
$ cargo build --release
```

or

```
$ docker build .
```

inside the repository.


## Running

Run either the binary produced by cargo, the Docker container you just built (using docker-compose) or pull the image
from [Docker Hub](https://hub.docker.com/r/vbrandl/hits-of-code)

```
$ docker run -it --rm vbrandl/hits-of-code --help
```

When running the binary directly, you need a git binary in your `PATH`.


## License

`hoc` is licensed under the MIT License ([LICENSE](LICENSE) or http://opensource.org/licenses/MIT)
