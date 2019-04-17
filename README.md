# Hits-of-Code

![Hits-of-Code](https://hitsofcode.com/github/vbrandl/hoc)
![[Docker build](https://img.shields.io/docker/cloud/build/vbrandl/hits-of-code.svg)](https://hub.docker.com/r/vbrandl/hits-of-code)

Small webservice, that returns a badge of the Hits-of-Code of a git repository, as described by [Yegor
Bugayenko](https://www.yegor256.com/2014/11/14/hits-of-code.html). Currently only GitHub repositories are supported, but
it can be trivially extended to support other platforms such as GitLab or Bitbucket.

A live version of this API can be found on [hitsofcode.com](https://hitsofcode.com/).

## API

The API is as simple as

```
https://<host>/<service>/<user>/<repo>
```

where `<service>` is one of `gitub`, `gitlab` or `bitbucket`.


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


## TODO

* [ ] Customization of badges (e.g. colors)
* [x] Support other platforms beside GitHub (GitLab and Bitbucket)
* [ ] Allow exclusion of certain files/globs from the HoC count

## License

`hoc` is licensed under the MIT License ([LICENSE](LICENSE) or http://opensource.org/licenses/MIT)
