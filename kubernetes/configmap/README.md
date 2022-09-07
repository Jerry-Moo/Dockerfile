## Namespace

```
kubectl apply -f hellok8s-config-dev.yaml -n dev

# configmap/hellok8s-config created

kubectl apply -f hellok8s-config-test.yaml -n test

# configmap/hellok8s-config created

kubectl get configmap --all-namespaces
NAMESPACE NAME DATA AGE
dev hellok8s-config 1 3m12s
test hellok8s-config 1 2m1s
```

## Deployment

```
kubectl apply -f hellok8s.yaml -n dev

# pod/hellok8s-pod created

kubectl apply -f hellok8s.yaml -n test

# pod/hellok8s-pod created

kubectl port-forward hellok8s-pod 3000:3000 -n dev

curl http://localhost:3000

# [v4] Hello, Kubernetes! From host: hellok8s-pod, Get Database Connect URL: http://DB_ADDRESS_DEV

kubectl port-forward hellok8s-pod 3000:3000 -n test

curl http://localhost:3000

# [v4] Hello, Kubernetes! From host: hellok8s-pod, Get Database Connect URL: http://DB_ADDRESS_TEST

```
