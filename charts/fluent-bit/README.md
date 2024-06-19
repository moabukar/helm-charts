# Deploy fluent bit on your K8s clusters via Helm

## How to:

- Depending on your output location, you need to generate API tokens etc

In this case, we dump logs to our Azure logs analytics workspace

- Create a secret with your keys:

```bash

apiVersion: v1
kind: Secret
metadata:
  name: fluent-bit-secrets
  namespace: kube-system
type: Opaque
data:
  customer_id: ## add base 64 encoded keys here (get from Azure portal)
  shared_key: ## add base 64 encoded keys here (get from Azure portal)


```

- Check daemons sets or pods are ready `k -n kube-system get pods | grep fluent-bit` and get logs `k -n kube-system logs <fluent-bit-podname>`

- Then apply Helm chart `helm install fluent-bit . -n kube-system`


To uninstall `helm uninstall fluent-bit . -n kube-system`
