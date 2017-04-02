# alpine-pkg-cmigemo
This is a cmigemo package for Alpine Linux.

## How to build a package
You can build a package by using [ttanjo/alpine-pkg-cmigemo](https://hub.docker.com/r/ttanjo/alpine-pkg-cmigemo/).
It generates APK packages for `cmigemo`, `cmigemo-dev` and `cmigo-doc` in `$PWD/packages`.
```
$ docker run -v $PWD/packages:/packages -v ~/.abuild:/home/builder/.abuild:ro --rm ttanjo/alpine-pkg-cmigemo
```

I assume that `~/.abuild` contains a private key file and `abuild.conf` (for environment variables).

Here is an example:
```
PACKAGER_PRIVKEY="/home/builder/.abuild/private-key.rsa"
PACKAGER='Tomoya Tanjo <ttanjo@gmail.com>'
```
