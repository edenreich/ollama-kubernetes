# Deploy Ollama onto Kubernetes

A POC on How-to deploy Ollama onto Kubernetes.

## Dependencies

- flox
- docker

## Quick Start

1. `flox activate`
2. `task cluster-create`
3. `kubectl apply -f ollama/`
4. `kubectl apply -f openweb-ui/`

## UI

Run: `kubectl port-forward svc/openweb-ui-service 8080:8080`

Open: `http://localhost:8080`

Create a dummy first account.

## Troubleshooting

The logs of ollama Kubernetes operator:
```
kubectl -n ollama-operator-system logs deploy/ollama-operator-controller-manager -f
```

The logs of the ollama API to troubleshoot the models being downloaded or any other issues related to API:
```
kubectl logs ollama-models-store-0 -f
```
