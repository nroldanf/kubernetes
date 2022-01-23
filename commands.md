# Kubernetes Install and Your First Pods

## Kubernetes Local Install

http://play-with-k8s.com

katacoda.com

### minikube

https://minikube.sigs.k8s.io/docs/start/

minikube start --driver docker

minikube status

### kind

kind version

kind create cluster --name <cluster_name> --config <config_file.yaml>

### microk8s

microk8s.kubectl

microk8s.enable dns

alias kubectl=microk8s.kubectl

## Change of context

kubectl config view

kubectl config get-contexts

kubectl config use-context <name_of_context>

## Kubectl run, create and apply

kubectl run

kubectl create

kubectl apply

## Our First Pod With Kubectl run

kubectl version

kubectl run my-nginx --image nginx

kubectl get ns/ kubectl get namespaces

kubectl get pods -n <namespace_name>

kubectl get all

kubectl delete deployment my-nginx

kubectl get all

## Get more information about entities

kubectl describe pods <pod_name> -n <namespace_name>

kubectl logs <pod_name> -n <namespace_name> -c <container_name>

## Run a command within a container inside a pod

kubectl exec --stdin --tty <pod_name> -n <namespace_name> -c <container_name> -- <command>

## Scaling ReplicaSets

kubectl run my-apache --image httpd

kubectl get all

kubectl scale deploy/my-apache --replicas2

kubectl scale deployment my-apache --replicas2

kubectl get all

## Inspecting Kubernetes Objects

kubectl get pods

kubectl logs deployment/my-apache

kubectl logs deployment/my-apache --follow --tail 1

kubectl logs -l run=my-apache

kubectl get pods

kubectl describe pod/my-apache-<pod id>

kubectl get pods -w

kubectl delete pod/my-apache-<pod id>

kubectl get pods

kubectl delete deployment my-apache

## helm

Find, install and publish Kubernetes packages: https://artifacthub.io/packages

```
helm repo add apache-airflow https://airflow.apache.org/
```

```
helm repo list
```

Search a chart in a repo (artifact hub by default):
```
helm search airflow
```

Download chart locally:
```
helm pull apache-airflow/airflow
```

Install from local directory:
```
helm install -g --debug <path>
```

Port forwarding to access Airflow UI for debug purposes:
```
kubectl get svc
kubectl port-forward svc/$RELEASE_NAME-webserver 8080:8080 --namespace $NAMESPACE
```

List helm releases:
```
helm ls
```

Upgrade:
```
helm upgrade --install <release_name> <repo_name> -f <values.yaml path> --debug --timeout 10m0s
```



