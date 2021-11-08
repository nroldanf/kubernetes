# kubectl (Kube Control)

3 ways to create pods:

Just for pod creation:

```
kubectl run
```

Create some additional resources via CLI or YAML

```
kubectl create
```

Create/update anything via YAML

```
kubectl apply
```

## Scaling

Start a new deployment for one replica/pod

```
kubectl create deployment <deployment_name> --image <image_name>
```

Scale it up with another pod:

```
kubectl scale deploy/<deployment_name> --replicas <num_replicas>
kubectl scale deployment <deployment_name> --replicas <num_replicas>
```

Check the pods states (watching constantly):

```
kubectl get pods -w
```

## Exposing containers

- `kubectl expose` creates a `service` for existing pods.
- A `service` is a stable address for pod(s). If we want to connect to pods we need a `service`.
- A service can be resolve by its IP and name (this one thanks to CodeDNS).

There are different types of services:
- __ClusterIP (Default)__: Only reachable from within the cluster
- __NodePort__
- __LoadBalancer__

