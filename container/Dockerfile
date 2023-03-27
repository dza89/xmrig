FROM alpine 

RUN mkdir /opt/xmrig && \
    wget "https://github.com/xmrig/xmrig/releases/download/v6.19.1/xmrig-6.19.1-linux-x64.tar.gz" && \
    tar -zxvf xmrig-6.19.1-linux-x64.tar.gz --strip-components 1 -C /opt/xmrig && \
    mv /opt/xmrig/xmrig /xmrig

ENTRYPOINT [/xmrig -c opt/xmrig/config.json]