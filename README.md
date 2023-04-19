# kubeflow-with-gitops

## Deployment

### Install Cluster

```sh
eksctl create cluster -f eks/eksctl.yaml
```

### Install ArgoCD

```sh
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Port-forward arogcd service in another terminal

```sh
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Get initial password.

```sh
argocd admin initial-password -n argocd
```

Copy the password and login.

```sh
argocd login localhost:8080
```
