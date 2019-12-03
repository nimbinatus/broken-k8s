The third playground seems healthy, but it's not. Why are pods getting restarted?

## Local Deployment with Minikube

First, you'll need to ensure you've got minikube running.

Set minikube to be able to use local images.
```bash
$ eval $(minikube docker-env)
```
Change directories to the `broken-k8s/broken3` directory in your terminal.

Create the namespace, service, and deployment.
```bash
$ kubectl create -f ./config/namespace.yaml
namespace/broken3 created
$ kubectl create -f ./config/deployment.yaml
deployment.apps/broken3 created
```

Check that everything is "running".
```bash
$ kubectl get all -n broken3
```

Wait a bit and check again, the pods keep restarting, can you figure out why?
