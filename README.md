# frp
Docker Image packaging for Frp.

(amd64, arm32v6, arm32v7, arm64v8, i386)

## Usage 
start frps
```
docker run --restart=always --network host -d -v /etc/frp/frps.ini:/etc/frp/frps.ini --name frps chendachao/frps
```

start frpc
```
docker run --restart=always --network host -d -v /etc/frp/frpc.ini:/etc/frp/frpc.ini --name frpc chendachao/frpc
```

## Quick reference
* Where to file issues:

[https://github.com/chendachao/frp/issues](https://github.com/chendachao/frp/issues)

* Maintained by:

snowdream <sn0wdr1am@icloud.com>

* Supported architectures: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))

frpc:

[amd64](https://cloud.docker.com/u/chendachao/repository/docker/chendachaoamd64/frpc), 
[arm32v6](https://cloud.docker.com/u/chendachao/repository/docker/chendachaoarm32v6/frpc), 
[arm32v7](https://cloud.docker.com/u/chendachao/repository/docker/chendachaoarm32v7/frpc),
[arm64v8](https://cloud.docker.com/u/chendachao/repository/docker/chendachaoarm64v8/frpc), 
[i386](https://cloud.docker.com/u/chendachao/repository/docker/chendachaoi386/frpc)

frps:

[amd64](https://cloud.docker.com/u/chendachaoamd64/repository/docker/chendachaoamd64/frps), [arm32v6](https://cloud.docker.com/u/chendachaoarm32v6/repository/docker/chendachaoarm32v6/frps), [arm32v7](https://cloud.docker.com/u/chendachaoarm32v7/repository/docker/chendachaoarm32v7/frps), [arm64v8](https://cloud.docker.com/u/chendachaoarm64v8/repository/docker/chendachaoarm64v8/frps), [i386](https://cloud.docker.com/u/chendachaoi386/repository/docker/chendachaoi386/frps)

* Supported Tags:

[Frps](https://cloud.docker.com/u/chendachao/repository/docker/chendachao/frps/tags)

[Frpc](https://cloud.docker.com/u/chendachao/repository/docker/chendachao/frpc/tags)

## License
Apache 2.0