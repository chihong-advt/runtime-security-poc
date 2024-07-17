# KubeArmor Operator Helm Chart
The official [KubeArmor Operator Helm Chart](https://github.com/kubearmor/KubeArmor/tree/main/deployments/helm/KubeArmorOperator)

## Setup
To test the KubeArmor in BSP Staging Cluster, kindly follow the steps below.
```bash
# there is a default deny-all network policy in the namespace
kubectl apply -f .

# apply policies
kubectl apply -f policies
```

## Info
- There is a [bug in version 1.3.4](https://github.com/kubearmor/KubeArmor/issues/1794).
- Version 1.3.8 supports cluster-level policy (stable release is not ready).

## Uninstall
```bash
kubectl delete -f .
kubectl delete -f policies
kubectl delete ns kubearmor
```
