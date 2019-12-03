This second playground is broken in two ways that you will need to figure out.

## Local Deployment with Minikube

First, you'll need to ensure you've got minikube running.

Set minikube to be able to use local images.
```bash
$ eval $(minikube docker-env)
```
Change directories to the `broken-k8s/broken2` directory in your terminal.

Create the namespace, service, and deployment.
```bash
$ kubectl create -f ./config/namespace.yaml
namespace/broken2 created
$ kubectl create -f ./config/service.yaml
service/broken2 created
$ kubectl create -f ./config/deployment.yaml
deployment.apps/broken2 created
```

Check that everything is "running" and that the service has endpoints.
```bash
$ kubectl get all -n broken2
$ kubectl get ep -n broken2
```

Things to solve:
* Why aren't your pods running? You can fix it in config, but can you also fix it imperatively?
* Once your pods are running, the service still has no endpoints, what's going on?
