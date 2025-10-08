 07-10-2025 03:17

Tags: [[Kubernetes]] [[Note]]
# **Helm Chart structure**

### What is a Helm Chart?

- A **package** of Kubernetes YAML files with templating 
- Contains: 
    - `Chart.yaml`: metadata 
    - `values.yaml`: default user-supplied values 
    - `templates/`: all K8s manifests 

### Chart Folder Structure

```
my-chart/
  Chart.yaml
  values.yaml
  templates/
    deployment.yaml
    service.yaml
    ingress.yaml
``` 

### Commands

- Install: `helm install my-release ./my-chart` 
- Upgrade: `helm upgrade my-release ./my-chart 
- Uninstall: `helm uninstall my-release 

### Benefits

- Reusability via templates 
- Customization via `values.yaml 
- Supports rollbacks and versioning 

---

References: [[Kubernetes Course Notes]]