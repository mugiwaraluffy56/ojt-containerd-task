### Problem-A - ImagePullBackOff
#### [evidences](commands.md#image-error)

- i changed the application image from task-ojt:v1 to task-ojt:v999, and the new kubernetes pod failed to start and entered the `ImagePullBackOff` state.

- used `kubectl get pods` to identify the failing pod and `kubectl describe pod` to inspect its events. the evidence indicated that kubernetes could not retrieve the specified image.

- the image tag `v999` did not exist.

- so i restored the correct image using `kubectl set image deployment/task-ojt task-ojt=task-ojt:v1`

- confirmed the deployment recovery `2/2 READY` using `kubectl get deployments`

### Problem-B - Application health
#### [evidences](commands.md#application-health)