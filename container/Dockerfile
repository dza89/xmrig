FROM alpine as prepare

RUN echo 'https://dl-cdn.alpinelinux.org/alpine/edge/community' >> /etc/apk/repositories
RUN apk add git make cmake libstdc++ gcc g++ automake libtool autoconf \
    linux-headers hwloc-dev libuv-dev openssl libressl-dev

RUN git clone https://github.com/xmrig/xmrig.git /xmrig && \
    cd /xmrig && git checkout v6.19.1

WORKDIR /xmrig/scripts
RUN mkdir -p /xmrig/build && chmod 755 *.sh\
    ./build_deps.sh
WORKDIR /xmrig/build
RUN cmake .. -DXMRIG_DEPS=scripts/deps -DBUILD_STATIC=ON -DHWLOC_LIBRARY=/usr/lib/libhwloc.so \
    -DWITH_OPENCL=OFF -DWITH_CUDA=OFF && \
    make -j$(nproc) 

FROM alpine
COPY --from=prepare /xmrig/build/xmrig /xmrig/xmrig
ENTRYPOINT ["/xmrig/xmrig", "-c", "opt/xmrig/config.json"]