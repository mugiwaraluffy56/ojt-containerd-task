## docker image verification

```bash
$ docker images
```
![alt text](screenshots/image-1.png)

```bash
$ docker ps
```
![alt text](screenshots/image-0.png)

## kubernetes image verification

```bash
$ kubectl get pods 
```
![alt text](screenshots/image-2.png)

```bash
$ kubectl get svc
```
![alt text](screenshots/image-3.png)

```bash
$ kubectl get deployments 
```
![alt text](screenshots/image-4.png)

```bash
$ kubectl get nodes -o wide
```
![alt text](screenshots/image-7.png)

## crictl tool exploration

```bash
$ crictl images
```
![alt text](screenshots/image-5.png)

```bash
$ crictl ps
```
![alt text](screenshots/image-6.png)


## image error

```bash
$ kubectl get pods
```
![alt text](screenshots/image-9.png)

```bash
$ kubectl describe pod task-ojt-7f7cfcdd68-75k5t
```
![alt text](screenshots/image-8.png)

```bash
$ kubectl rollout status deployment/task-ojt
$ kubectl get pods
$ kubectl get deployments
```
![alt text](screenshots/image-10.png)

## application health

```bash
$ kubectl get pods
```
![alt text](screenshots/image-11.png)

```bash
$ kubectl describe pod task-ojt-7f84f5fd5d-mvbjd
```
![alt text](screenshots/image-12.png)

```bash
$ kubectl get deployments
```
![alt text](screenshots/image-13.png)

## service connectivity

```bash
$ kubectl describe svc task-ojt
```
![alt text](screenshots/image-14.png)