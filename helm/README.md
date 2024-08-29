# Start Minikube with mockserver
```


docker system prune
minikube start
minikube addons enable metrics-server
minikube dashboard
```

Load the image in minikube

```
docker pull mockserver/mockserver:mockserver-5.14.0
minikube image load mockserver/mockserver:mockserver-5.15.0
```

Install mockserver using helm chart

```
helm repo add mockserver https://www.mock-server.com
helm repo update
helm upgrade --install --version 5.15.0 mockserver mockserver/mockserver
```

Access from minikube

```
minikube service mockserver
```

Get the URL and access to this path: `http://127.0.0.1:<PORT>/mockserver/dashboard`





## Comandos Helm

helm list -n mockserver
helm uninstall mockserver -n mockserver


## Comandos kubectl

kubectl get pods -n mockserver
kubectl describe pod mockserver-69dbfb787f-szs9j -n mockserver