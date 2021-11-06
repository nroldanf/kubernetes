# Kubernetes (K8s)

Kubernetes is an open source tool for managing, automating deployment, scaling of containerized application. Also known as an orchestration tool for container workloads.

A set of APIs that runs on top of Docker (you still can use another container runtime e.g. containerd). It's just a series of containers that manages those APIs to manage the multinode system.

Kube control: CLI to manage containers across servers with k8s
```
kubectl
```

__How do you get it?__

Usually from a cloud vendor that provides K8s as a service (APIs and GUIs). Other vendors package their own version of K8s as "distributions" similar as Linux distributions. But they are fundamentally the same, based on the pure open-source K8s.

## Why K8s?

Why you may need orchestration?

- Many people already are just running their containers with `docker run` and adding load balancing, auto-scaling groups and many other things to build a similar orchestration solution.
- It depends of `how fast your applications need to change` and `how many server you might need`
- If you don't change you applicaitons very often (once a month or less), orchestration might not be necessary.

__Which orchestrator to choose?__

- Swarm: Easier to deploy/manage.
- K8s: Hybrid can be run in multiple clouds or on-premises. Customizable and flexible. Wider adoption and support.
- ECS (AWS legacy solution before K8s): AWS specific offering.
...

__Which distribution are you going to use?__

- EKS
- Rancher
- OpenShift (RedHat)
- Canonical K8s
- PKS (VMWare)
- Raw Open Source K8s: https://github.com/kubernetes/kubernetes
...

Vendors products usually are just one version outdated, but they try to stay updated. Vendor solutions have custom authentication, custom web admin, custom networking, etc.

More [Kubernetes Certified Distributions](https://kubernetes.io/partners/#conformance)


Running first pod with k8s. This only creates a `pod` named `my-nginx` using `nginx` docker image.

```
kubectl run my-nginx --image nginx
```

To see the pods:

```
kubectl get pods
```

To see everything (including `services`):

```
kubectl get all
```

To delete a pod:

```
kubectl delete pod my-nginx
```