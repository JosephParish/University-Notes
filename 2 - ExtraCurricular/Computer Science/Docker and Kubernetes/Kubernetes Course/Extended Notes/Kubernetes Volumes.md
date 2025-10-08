 07-10-2025 03:15

Tags: 
# **Kubernetes Volumes**

### Volume Types

- `emptyDir`: Temporary pod-level storage 
- `hostPath`: Mounts node's filesystem into pod 
- `configMap` / `secret`: Mounts config/secrets as volumes 

### Persistent Volumes (PV) & Claims (PVC)

- **PersistentVolume (PV)**: Defines actual storage resource 
- **PersistentVolumeClaim (PVC)**: Request by pods to use storage

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
```

### StorageClass

- Automates dynamic provisioning 
- Abstracts provider-specific volume creation (e.g., EBS, AzureDisk)

References: [[Kubernetes Course Notes]]