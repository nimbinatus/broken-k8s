This first playground has a fairly obvious bug if you know where to look!



## Local Deployment with Minikube

First, you'll need to ensure you've got minikube running.

Set minikube to be able to use local images.
```bash
$ eval $(minikube docker-env)
```
Change directories to the `broken-k8s/broken1` directory in your terminal.

Build the docker image from this directory.
```bash
$ docker build -t broken1 .
Sending build context to Docker daemon  9.728kB
Step 1/17 : FROM python:alpine
...
Successfully tagged broken1:latest
```

Create the namespace, service, and deployment.
```bash
$ kubectl create -f ./config/namespace.yaml
namespace/broken1 created
$ kubectl create -f ./config/service-broken1.yaml
service/broken1 created
$ kubectl create -f ./config/deployment.yaml
deployment.apps/broken1 created
```

Check that everything is "running".
```bash
$ kubectl get all -n broken1
```

Now go fix it!
