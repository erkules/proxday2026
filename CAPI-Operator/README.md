```
helm repo add capi-operator https://kubernetes-sigs.github.io/cluster-api-operator
helm repo add jetstack https://charts.jetstack.io --force-update
helm repo update
helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --set installCRDs=true
helm install capi-operator capi-operator/cluster-api-operator --create-namespace -n capi-operator-system --wait --timeout 90s
```
