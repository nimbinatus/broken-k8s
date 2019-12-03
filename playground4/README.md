The fourth playground cannot seem to start any pods. What is missing?

## Local Deployment with Minikube

First, you'll need to ensure you've got minikube running.

Set minikube to be able to use local images.
```bash
$ eval $(minikube docker-env)
```
Change directories to the `broken-k8s/broken4` directory in your terminal.

Create the namespace, service, and deployment.
```bash
$ kubectl create -f ./config/namespace.yaml
namespace/broken4 created
$ kubectl create -f ./config/deployment.yaml
deployment.apps/broken4 created
```

Check that everything is "running".
```bash
$ kubectl get all -n broken4
```

Why aren't the pods starting?
