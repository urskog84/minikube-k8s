# minikube_k8s

minikube cluster wtith

- [x] argoCD

## Start minikube cluster
```bach
minikube start --cpus=8 --memory=12g --addons=ingress
```

## install argocd
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml




kubectl apply -n argocd -f apps/apps-app.yaml
```

# login to argo cd
```

kubectl port-forward -n argocd svc/argocd-server 8080:443 &

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo



```
