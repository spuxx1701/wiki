## Debug a pod

```bash
# Retrieve pods
kubectl get pod
# Open a terminal within a pod
kubectl exec -it some-pod-id -- bin/bash
# Exit
exit
```

## Apply a configuration file

```bash
kubectl apply -f foo.yaml
```
