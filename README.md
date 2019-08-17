# frp
Docker Image packaging for Frp.

(amd64, arm32v6, arm32v7, arm64v8, i386)

## Usage 
start frps
```
docker run --restart=always --network host -d -v /etc/frp/frps.ini:/etc/frp/frps.ini --name frps chendachao/frps
docker run --restart=always --network host -d -v $(pwd)/frps.ini:/etc/frp/frps.ini --name frps chendachao/frps
```

start frpc
```
docker run --restart=always --network host -d -v /etc/frp/frpc.ini:/etc/frp/frpc.ini --name frpc chendachao/frpc
docker run --restart=always --network host -d -v $(pwd)/frpc.ini:/etc/frp/frpc.ini --name frpc chendachao/frpc
```

## Quick reference
* Where to file issues:

[https://github.com/chendachao/frp/issues](https://github.com/chendachao/frp/issues)

* Maintained by:

chendachao<chendachao@outlook.com>

* Supported architectures: ([more info](https://github.com/docker-library/official-images#architectures-other-than-amd64))

frpc:

[amd64](https://cloud.docker.com/repository/docker/chendachao/frpc-amd64), 
[arm32v6](https://cloud.docker.com/repository/docker/chendachao/frpc-arm32v6), 
[arm32v7](https://cloud.docker.com/repository/docker/chendachao/frpc-arm32v7),
[arm64v8](https://cloud.docker.com/repository/docker/chendachao/frpc-arm64v8), 
[i386](https://cloud.docker.com/repository/docker/chendachao/frpc-i386)

frps:

[amd64](https://cloud.docker.com/repository/docker/chendachao/frps-amd64),
[arm32v6](https://cloud.docker.com/repository/docker/chendachao/frps-arm32v6), 
[arm32v7](https://cloud.docker.com/repository/docker/chendachao/frps-arm32v7), 
[arm64v8](https://cloud.docker.com/repository/docker/chendachao/frps-arm64v8), 
[i386](https://cloud.docker.com/repository/docker/chendachao/frps-i386)

* Supported Tags:

[Frps](https://cloud.docker.com/repository/docker/chendachao/frps/tags)

[Frpc](https://cloud.docker.com/repository/docker/chendachao/frpc/tags)

## License
Apache 2.0