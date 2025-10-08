 07-10-2025 03:13

Tags:  [[Kubernetes]] [[Note]]
# **StatefulSet vs Deployment**

### Deployment

- Best for **stateless** applications 
- Pods are interchangeable 
- Fast horizontal scaling 
- No persistent identity 

### StatefulSet

- Best for **stateful** applications (e.g. databases) 
- Each pod has: 
    - Stable hostname (`app-0`, `app-1`, …) 
    - Stable persistent volume 
    - Ordered, graceful deployment & scaling 

### When to Use:

- Use **Deployment** for APIs, frontends, web apps 
- Use **StatefulSet** for databases like MongoDB, Redis, PostgreSQL

References: [[Kubernetes Course Notes]]