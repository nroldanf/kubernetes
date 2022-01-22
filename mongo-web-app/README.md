# Mongo-db application

## mongo-config

- kind: ConfigMap
- metadata / name
- data: key-value contents. In this case reference a service.

## mongo-secret

- kind: Secret
- metadata / name
- type: facilitate programmatic handling of different kinds of confidential data. `Opaque` by default.
- data: key-value base64 encoded data (by default). Usually, use an external service.

Get encoded data as following:
```
echo -n mongouser | base64
echo -n mongopassword | base64
```

## mongo (deployment and service)

Usually, deployments and services are grouped in one yaml file.

### deployment

- kind: Deployment
- metadata / name, labels: a label is a key-value pair attached to a k8s resource. They are dditional identifiers. For pods, `labels` is a required field. 
- spec: deployment specific configuration.
    - replicas: how many pods are created using the same blueprint.
    - selector: How k8s knows which pods belong to a deployment.
    - template: a configuraiton for a pod. Has own `metadata` and `spec`.
        - spec:
            - containers

If we were using more than 1 `replica`, you should use `StatefulSet` instead of `Deployment`