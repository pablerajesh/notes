CKAD NOTES
==========

# Command-line General

## Kubectl Alias
```
# Cli help
$ kubectl run help

# Setup an alias
$ alias k=kubectl

# Execute command using alias
$ k version
```

## Context & Namespace
```
# Set context and namespace
$ kubectl config set-context <context-name> --namespace=<namespace>

# Use context
$ kubectl use context <context-name>
```

## Resources
```
# Get resource (note the short name)
$ kubectl get api-resources

NAME                    SHORTNAMES  APIGROUP    NAMESPACED KIND
...
persistentvolumeclaims  pvc         true        PersistentVolumeClaim
...

# Use the short name of the resource
$ kubectl use context <context-name>
```

# Application Design & Build

## Pod
```
$ kubectl run hazelcase --image hazelcast/hazelcast:5.1.7 --port=5701 --env"DNS_DOMAIN=cluster" --labels="app=hazelcast,env=prod"
```
```yml
apiVersion: v1
kind: Pod
metadata:
  name: hazelcast
  labels:
    app: hazelcast
    env: prod
spec:
  containers:
  - name: hazelcast
    image: hazelcast/hazelcast:5.1.7
    env:
    - name: DNS_DOMAIN
    value: cluster
    ports:
    - containerPort: 5701
```

