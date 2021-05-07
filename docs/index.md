# Introduction

[![](https://travis-ci.org/rexzhang/asgi-webdav.svg?branch=main)](https://travis-ci.org/rexzhang/asgi-webdav)
[![Coverage Status](https://coveralls.io/repos/github/rexzhang/asgi-webdav/badge.svg?branch=main)](https://coveralls.io/github/rexzhang/asgi-webdav?branch=main)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

An asynchronous WebDAV server implementation, Support multi-provider, multi-account and permission control.

## Features

- ASGI standard
- WebDAV standard: [RFC4918](https://www.ietf.org/rfc/rfc4918.txt)
- Support multi-provider: FileProvider, MemoryProvider
- Support multi-account and permission control
- Support Optional home directory
- Full asyncio file IO
- Passed all [litmus(0.13)](http://www.webdav.org/neon/litmus) test, except 2
  warning.
- Web dir browser
- Compatible macOS finder

## Quickstart

### Install to docker

```shell
docker pull ray1ex/asgi-webdav:latest
```

### Run it

```shell
docker run --restart always -p 0.0.0.0:80:80 -v /your/path:/data \
  --name asgi-webdav ray1ex/asgi-webdav
```

```text
WARNING: load config value from file[/data/webdav.json] failed, [Errno 2] No such file or directory: '/data/webdav.json'
INFO: [asgi_webdav.webdav] ASGI WebDAV(v0.3.1) starting...
INFO: [asgi_webdav.distributor] Mapping Prefix: / => file:///data
INFO: [asgi_webdav.auth] Register Account: username, allow:[''], deny:[]
INFO: [uvicorn] Started server process [7]
INFO: [uvicorn] Uvicorn running on http://0.0.0.0:80 (Press CTRL+C to quit)
```

### View in browser

Default account: `username`/`password`

![](web-dir-browser-screenshot.png)