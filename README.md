# Demo

## installere kubectl

https://kubernetes.io/docs/tasks/tools/#kubectl

## Installere Kind

se https://kind.sigs.k8s.io/

## kind demo opprett et kind cluster og deploy en applikasjon på clusteret

### opprett cluster

```bash
kind create cluster --config kind-cluster.yaml
```

### sett at kubectl bruker kind clusteret

```bash
kubectl cluster-info --context kind-tomvin-kind
```

### deploy ingress controller for reverse proxy og load balancer

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

### deploy applikasjonen vår

```bash
kubectl apply -f demo.yaml
```

### se status på service'ene på clusteret vårt

```bash
kubectl get services
```

### servicen er deployet kan man nå servicen fra localhost/tomvin

```bash
curl localhost/tomvin
```

### slett clusteret vårt

```bash
kind delete cluster --name tomvin-kind
```
