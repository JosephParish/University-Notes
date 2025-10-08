 07-10-2025 03:07

Tags:  [[Kubernetes]] [[Note]]
# **kubectl cheat sheet**

### Basic Commands
- `kubectl version`
- `kubectl cluster-info`
- `kubectl get nodes`
- `kubectl get all`

### Working with Pods
- `kubectl get pods`
- `kubectl describe pod <pod-name>`
- `kubectl logs <pod-name>`
- `kubectl exec -it <pod-name> -- /bin/sh`

### Apply & Delete Resources
- `kubectl apply -f deployment.yaml`
- `kubectl delete -f deployment.yaml`

### Namespace Commands
- `kubectl get namespaces`
- `kubectl config set-context --current --namespace=<ns>`

### Scaling
- `kubectl scale deployment <name> --replicas=5`

### Rollouts
- `kubectl rollout status deployment/<name>`
- `kubectl rollout undo deployment/<name>`

References: [[Kubernetes Course Notes]]