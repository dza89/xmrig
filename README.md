# xmrig

A plain xmrig container and deployment, nothing more nothing less.

## Install

Minimum values needed:
All configurables from [xmrig-example-configs](https://github.com/xmrig/xmrig/blob/master/src/config.json) can be set under config.

```yaml
config:
    pools:
        - algo:
          coin:
          url: donate.v2.xmrig.com:3333
          user: YOUR_WALLET_ADDRESS
```

```bash
helm repo add xmrig https://dza89.github.io/xmrig
helm repo update
helm upgrade xmrig --install xmrig/xmrig -f values.yaml
```
