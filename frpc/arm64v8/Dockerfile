# FROM arm64v8/alpine:3.10

# ENV FRP_VERSION 0.28.2

# VOLUME [ "/sys/fs/cgroup" ]

# COPY qemu-aarch64-static /usr/bin

# RUN apk add --no-cache openrc \
#     && cd /root \
#     &&  wget -c https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_arm64.tar.gz \
#     &&  tar zxvf frp_${FRP_VERSION}_linux_arm64.tar.gz  \
#     &&  cd frp_${FRP_VERSION}_linux_arm64/ \
#     &&  cp frpc /usr/bin/ \
#     &&  mkdir -p /etc/frp \
#     &&  cp frpc.ini /etc/frp \
#     &&  cd /root \
#     &&  rm frp_${FRP_VERSION}_linux_arm64.tar.gz \
#     &&  rm -rf frp_${FRP_VERSION}_linux_arm64/ 

# ENTRYPOINT /usr/bin/frpc -c /etc/frp/frpc.ini

FROM alpine:3.10 AS builder

ENV FRP_VERSION 0.28.2

RUN apk add --no-cache openrc \
    && cd /root \
    &&  wget -c https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_arm64.tar.gz \
    &&  tar zxvf frp_${FRP_VERSION}_linux_arm64.tar.gz  \
    &&  cd frp_${FRP_VERSION}_linux_arm64/ \
    &&  cp frpc /usr/bin/ \
    &&  mkdir -p /etc/frp \
    &&  cp frpc.ini /etc/frp \
    &&  cd /root \
    &&  rm frp_${FRP_VERSION}_linux_arm64.tar.gz \
    &&  rm -rf frp_${FRP_VERSION}_linux_arm64/  

FROM arm64v8/alpine:3.10

VOLUME [ "/sys/fs/cgroup" ]

COPY --from=builder /usr/bin/frpc  /usr/bin/frpc
COPY --from=builder /etc/frp  /etc/frp
COPY qemu-aarch64-static /usr/bin

ENTRYPOINT /usr/bin/frpc -c /etc/frp/frpc.ini