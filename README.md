# doks-sealed-secrets
1. `helm repo add bitnami https://charts.bitnami.com/bitnami`
2. `helm repo update`
3. `helm install sealed-secrets-controller bitnami/sealed-secrets -n kube-system`
4. Install kubeseal CLI (on Mac: `brew install kubeseal`)
5. `kubeseal < mysecret.yaml > mysealedsecret.yaml`
6. `kubectl apply -f mysealedsecret.yaml`
7. Edit mycrtsecret.yaml file with base64 encodings of the crt and key, which can be obtained with following commands:
   `cat tls.crt | base64 -w 0`
   `cat tls.key | base64 -w 0`
8. `kubeseal < mycrtsecret.yaml > mysealedcrtsecret.yaml`
9. `kubectl apply -f mysealedcrtsecret.yaml`

SealedSecret yaml files contain encrypted secrets which can safely be committed to source control.
