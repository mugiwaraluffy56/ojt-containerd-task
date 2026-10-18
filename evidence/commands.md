## docker image verification

```bash
$ docker images
```
![alt text](screenshots/task1-docker-images.png)

```bash
$ docker ps
```
![alt text](screenshots/task1-docker-ps.png)

## kubernetes image verification

```bash
$ kubectl get pods 
```
![alt text](screenshots/task2-kubernetes-pods.png)

```bash
$ kubectl get svc
```
![alt text](screenshots/task2-kubernetes-services.png)

```bash
$ kubectl get deployments 
```
![alt text](screenshots/task2-kubernetes-deployments.png)

```bash
$ kubectl get nodes -o wide
```
![alt text](screenshots/task3-container-runtime.png)

## crictl tool exploration

```bash
$ crictl images
```
![alt text](screenshots/task3-crictl-images.png)

```bash
$ crictl ps
```
![alt text](screenshots/task3-crictl-containers.png)


## image error

```bash
$ kubectl get pods
```
![alt text](screenshots/task4a-image-error-status.png)

```bash
$ kubectl describe pod task-ojt-7f7cfcdd68-75k5t
```
![alt text](screenshots/task4a-image-error-events.png)

```bash
$ kubectl rollout status deployment/task-ojt
$ kubectl get pods
$ kubectl get deployments
```
![alt text](screenshots/task4a-image-error-recovery.png)

## application health

```bash
$ kubectl get pods
```
![alt text](screenshots/task4b-healthcheck-status.png)

```bash
$ kubectl describe pod task-ojt-7f84f5fd5d-mvbjd
```
![alt text](screenshots/task4b-healthcheck-events.png)

```bash
$ kubectl get deployments
```
![alt text](screenshots/task4b-healthcheck-recovery.png)

## service connectivity

```bash
$ kubectl describe svc task-ojt
```
![alt text](screenshots/task4c-service-port-error.png)