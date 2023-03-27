# xmrig

A plain xmrig container and deployment, nothing more nothing less.
Configure with `-f ./xmrig-config.json`, see [xmrig-example-configs](https://github.com/xmrig/xmrig/blob/master/src/config.json)

## Install

```bash
helm repo add xmrig https://dza89.github.io/xmrig
helm repo update
helm upgrade xmrig --install xmrig/xmrig \
    -f ./xmrig-config.json
```
