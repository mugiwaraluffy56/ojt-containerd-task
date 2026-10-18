## overview
a simple Flask application containerized using Docker and deployed to a local Kubernetes cluster using kind.

## tech stack
- python + flask
- docker
- kubernetes (kind)
- containerd

## API endpoints

| endpoint | eescription |
|---|---|
| `GET /` | returns a welcome message |
| `GET /health` | returns application health status |

## prerequisites
- Python 3
- Docker
- kind
- kubectl

## run with Docker

```bash
docker build -t student-app:v1 .
docker run -d --name student-app -p 5000:5000 student-app:v1
```

test the application:

```bash
curl http://localhost:5000/
curl http://localhost:5000/health
```

## deploy to Kubernetes

```bash
kind create cluster --name student-cluster
kind load docker-image student-app:v1 --name student-cluster
kubectl apply -f k8s/
kubectl get pods
kubectl get services
```

access the Service:

```bash
kubectl port-forward svc/student-app 8080:5000
```

test through the Service:

```bash
curl http://localhost:8080/
curl http://localhost:8080/health
```

## container Runtime

the kind node uses containerd. see [commands.md](evidence/commands.md) for the runtime inspection commands and outputs.

## troubleshooting

three failures were intentionally introduced and resolved:

1. invalid container image reference
2. incorrect application health-check path
3. incorrect Kubernetes Service target port

see [troubleshooting.md](evidence/troubleshooting.md) for diagnostics and fixes.

## evidence

screenshots and terminal outputs are available in `evidence/`.
