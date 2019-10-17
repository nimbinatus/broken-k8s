As a note, this one should work, not fail. It's a tester system to ensure that you don't have an error with your system overall.

## Local Deployment with Minikube

First, you'll need to ensure you've got minikube running.

Set minikube to be able to use local images.
```bash
$ eval $(minikube docker-env)
```
Change directories to the `broken-k8s/base-k8s` directory in your terminal.

Build the docker image from this directory.
```bash
$ docker build -t base-k8s .
Sending build context to Docker daemon  9.728kB
Step 1/17 : FROM python:alpine
...
Successfully tagged base-k8s:latest
```

Create the namespace, service, and deployment.
```bash
$ kubectl create -f ./config/namespace.yaml
namespace/base-k8s created
$ kubectl create -f ./config/service-base.yaml
service/base-k8s created
$ kubectl create -f ./config/deployment.yaml
deployment.apps/base-k8s created
```

Check that everything is running.
```bash
$ kubectl get all
NAME                            READY   STATUS    RESTARTS   AGE
pod/base-k8s-5dc55c4649-5gqs5   1/1     Running   0          3m56s
pod/base-k8s-5dc55c4649-n95xd   1/1     Running   0          3m56s
pod/base-k8s-5dc55c4649-tznls   1/1     Running   0          3m56s


NAME               TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
service/base-k8s   NodePort   10.97.212.255   <none>        5000:31066/TCP   9m28s


NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/base-k8s   3/3     3            3           3m56s

NAME                                  DESIRED   CURRENT   READY   AGE
replicaset.apps/base-k8s-5dc55c4649   3         3         3       3m56s
```

Get the local URL to check that you get good output.
```bash
$ minikube service base-k8s --url -n base-k8s
```