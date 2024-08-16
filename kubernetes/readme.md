CKAD NOTES
==========

# Command-line General

## Kubectl Alias
```bash
# Setup an alias
$ alias k=kubectl

# Execute command using alias
$ k version
```

## Context & Namespace
```bash
# Set context and namespace
$ kubectl config set-context <context-name> --namespace=<namespace>

# Use context
$ kubectl use context <context-name>
```

## Resources
```bash
# Get resource (note the short name)
$ kubectl get api-resources

NAME                    SHORTNAMES  APIGROUP    NAMESPACED KIND
...
persistentvolumeclaims  pvc         true        PersistentVolumeClaim
...

# Use the short name of the resource
$ kubectl use context <context-name>
```