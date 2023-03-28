# xmrig

A plain xmrig container and deployment, nothing more nothing less.

## Install

All configurables from [xmrig-example-configs](https://github.com/xmrig/xmrig/blob/master/src/config.json) can be set under config.
A full list can be found in [chart value file](./charts/xmrig/values.yaml). Any unspecified keys will still work.

!!! warning
This pod runs privileged in your cluster!! 

Minimum values needed:

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
