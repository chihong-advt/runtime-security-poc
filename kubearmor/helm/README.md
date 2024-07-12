# KubeArmor Operator Helm Chart
The official [KubeArmor Operator Helm Chart](https://github.com/kubearmor/KubeArmor/tree/main/deployments/helm/KubeArmorOperator)

## Setup
```bash
helm repo add kubearmor https://kubearmor.github.io/charts
helm repo update kubearmor
helm upgrade --install kubearmor-operator kubearmor/kubearmor-operator --set autoDeploy=true -n kubearmor --create-namespace

# there is a default deny-all network policy in the namespace
kubectl delete netpol default-deny -n kubearmor
kubectl apply -f netpol.yaml

# apply policies
kubectl apply -f policies
```

## Uninstall
```bash
helm delete kubearmor-operator -n kubearmor
kubectl delete -f netpol.yaml
kubectl delete -f policies
```
