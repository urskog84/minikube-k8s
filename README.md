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

kubectl port-forward -n argocd svc/argocd-server 8080:443 & /
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo



```

# X-fowrwad-\* hedder

```
k edit svc -n kube-system traefik

editera
spec:
  .
  .
  externalTrafficPolicy: Cluster --> to
externalTrafficPolicy: Local
```

(
NAMESPACE=argocd
kubectl proxy &
kubectl get namespace $NAMESPACE -o json |jq '.spec = {"finalizers":[]}' >temp.json
curl -k -H "Content-Type: application/json" -X PUT --data-binary @temp.json 127.0.0.1:8001/api/v1/namespaces/$NAMESPACE/finalize
)
