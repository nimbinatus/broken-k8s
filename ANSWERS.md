# STOP
# Only read this file AFTER you've tried solving the environments!

The whole point is to try to solve it yourself first :)

## playground1

Flask is a really, really old version that doesn't work with the syntax. It should also be broken for Python3, which is what the image is based on.

## playground2

There are two problems here. First the deployment specified 0 replicas which means no pods are running. Fix this in config or scale it imperatively with the scale command. Second the pod selector is wrong for the service which means the service has no endpoints.

## playground3

There is a liveness check defined with a bad URL. Use a URL that nginx will respond on.