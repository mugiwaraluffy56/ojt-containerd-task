### Problem-A - ImagePullBackOff

#### [screenshots](commands.md#image-error)

- i changed the application image from `task-ojt:v1` to `task-ojt:v999`, and the new kubernetes pod failed to start and entered the `ImagePullBackOff` state.

- used `kubectl get pods` to identify the failing pod and `kubectl describe pod` to inspect its events. the evidence indicated that kubernetes could not retrieve the specified image.

- the image tag `v999` did not exist.

- so i restored the correct image using `kubectl set image deployment/task-ojt task-ojt=task-ojt:v1`

- confirmed the deployment recovery `2/2 READY` using `kubectl get deployments`

---

### Problem-B - Application health

#### [screenshots](commands.md#application-health)

- i changed the kuberenetes readiness and liveness probe paths from `/health` to `/wrong-health` .

- used `kubectl get pods` to inspect pod readiness, `kubectl describe pod` to identify health check failures.

- the application doesn't expose `/wrong-health`, so health check requests return HTTP 404.

- restored the correct `/health` endpoint in both probes and reapplied the deployment configuration.

- confirmed the deployment recovery `2/2 READY` using `kubectl get deployments`

---

### Problem-C - Service connectivity

#### [screenshots](commands.md#service-connectivity)

- i changed the kubernetes service `targetPort` from `1234` to `9999`.

- used `kubectl get svc`, `kubectl describe svc` and `kubectl get endpointslice` to inspect the service config, tested the connectivity using `curl`

- the service forwarded traffic to port `9999` but the flask application was listening on port `1234`

- so i changed the service `targetPort` back to `1234` and reapplied the config.

- confirmed that both `/` and `/health` endpoints were accesible through the service.

