[https://github.com/moabukar/helm-charts](https://github.com/moabukar/helm-charts)

# Usage

```bash
~$ helm repo add moabukar https://charts.visonneau.uk/
~$ helm repo update
~$ helm search repo moabukar | awk '{print $1}' | tail -n +2

moabukar/tailscale-relay
```
