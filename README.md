# alpine-pkg-glog

[![CircleCI](https://img.shields.io/circleci/project/sgerrand/alpine-pkg-glog/master.svg)](https://circleci.com/gh/sgerrand/alpine-pkg-glog)

This is the [Google logging module][glog] as an Alpine Linux package.

## Releases

See the [releases page][releases] for the latest download links.

## Installing

The current installation method for these packages is to pull them in using
`wget` or `curl` and install the local file with `apk`:

```
apk --no-cache add ca-certificates
wget -q -O /etc/apk/keys/sgerrand.rsa.pub https://raw.githubusercontent.com/sgerrand/alpine-pkg-glog/master/sgerrand.rsa.pub
wget https://github.com/sgerrand/alpine-pkg-glog/releases/download/0.3.4-r0/glog-0.3.4-r0.apk
apk --allow-untrusted add glog-0.3.4-r0.apk
```

[glog]: https://github.com/google/glog
[releases]: https://github.com/sgerrand/alpine-pkg-glog/releases/
