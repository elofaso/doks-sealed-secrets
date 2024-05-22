# doks-sealed-secrets
1. `helm repo add bitnami https://charts.bitnami.com/bitnami`
2. `helm repo update`
3. `helm install sealed-secrets-controller bitnami/sealed-secrets -n kube-system`
4. Install kubseal CLI (on Mac: `brew install kubeseal`)
5. `kubeseal < secret.yaml > sealed-secret.yaml`
6. `kubectl apply -f sealed-secret.yaml`
