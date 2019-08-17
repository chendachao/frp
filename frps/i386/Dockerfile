# FROM i386/alpine:3.10

# ENV FRP_VERSION 0.28.2
# ENV QEMU_USER_STATIC_VERSION 4.0.0-5

# VOLUME [ "/sys/fs/cgroup" ]

# RUN apk add --no-cache openrc \
#     && cd /root \
#     &&  wget -c https://github.com/multiarch/qemu-user-static/releases/download/v${QEMU_USER_STATIC_VERSION}/x86_64_qemu-i386-static.tar.gz \
#     &&  tar zxvf x86_64_qemu-i386-static.tar.gz  \
#     &&  mv qemu-i386-static /usr/bin/  \
#     &&  rm x86_64_qemu-i386-static.tar.gz  \
#     &&  wget -c https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_386.tar.gz \
#     &&  tar zxvf frp_${FRP_VERSION}_linux_386.tar.gz  \
#     &&  cd frp_${FRP_VERSION}_linux_386/ \
#     &&  cp frps /usr/bin/ \
#     &&  mkdir -p /etc/frp \
#     &&  cp frps.ini /etc/frp \
#     &&  cd /root \
#     &&  rm frp_${FRP_VERSION}_linux_386.tar.gz \
#     &&  rm -rf frp_${FRP_VERSION}_linux_386/ 

# ENTRYPOINT /usr/bin/frps -c /etc/frp/frps.ini


FROM alpine:3.10 AS builder

ENV FRP_VERSION 0.28.2
ENV QEMU_USER_STATIC_VERSION 4.0.0-5

RUN apk add --no-cache openrc \
    && cd /root \
    &&  wget -c https://github.com/multiarch/qemu-user-static/releases/download/v${QEMU_USER_STATIC_VERSION}/x86_64_qemu-i386-static.tar.gz \
    &&  tar zxvf x86_64_qemu-i386-static.tar.gz  \
    &&  mv qemu-i386-static /usr/bin/  \
    &&  rm x86_64_qemu-i386-static.tar.gz  \
    &&  wget -c https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_386.tar.gz \
    &&  tar zxvf frp_${FRP_VERSION}_linux_386.tar.gz  \
    &&  cd frp_${FRP_VERSION}_linux_386/ \
    &&  cp frps /usr/bin/ \
    &&  mkdir -p /etc/frp \
    &&  cp frps.ini /etc/frp \
    &&  cd /root \
    &&  rm frp_${FRP_VERSION}_linux_386.tar.gz \
    &&  rm -rf frp_${FRP_VERSION}_linux_386/  

FROM i386/alpine:3.10

VOLUME [ "/sys/fs/cgroup" ]

COPY --from=builder /usr/bin/frps  /usr/bin/frps
COPY --from=builder /etc/frp  /etc/frp
COPY --from=builder /usr/bin/qemu-i386-static  /usr/bin/qemu-i386-static

ENTRYPOINT /usr/bin/frps -c /etc/frp/frps.ini
