# broken-k8s

A repo full of deliberately broken k8s setups to pull down and practice on.

## Who can use this repo?

Anyone! I was hunting for a set of deliberately broken k8s setups to use to teach debugging strategies for containerization and Kubernetes, but I couldn't find any. So I figured I would create my own. Y'all are welcome to join in!

## Answers

There is an answers file that explains what is wrong with each environment. Don't read it until you've worked toward solving the problem!

## Contributing

Please fork, create a branch, commit your work in atomic elements, and open a PR to contribute. I generally squash and merge or rebase and merge from the PR, so no need to squash it ahead of time if you don't want to.

Each environment should have its own directory that includes everything you need to start locally. Ensure you include a README in each directory with directions on how to start the environment locally (I've been using minikube). Try to avoid naming the directory or writing the README in such a way as to give away the problem people are solving for!

Note that you shouldn't submit fixes to make an environment work properly. That's not the point ;) 

Have fun!