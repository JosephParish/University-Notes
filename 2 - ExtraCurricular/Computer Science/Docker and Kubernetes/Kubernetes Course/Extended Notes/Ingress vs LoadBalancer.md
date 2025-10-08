 07-10-2025 03:14

Tags: [[Kubernetes]] [[Note]]
# **Ingress vs LoadBalancer**

### LoadBalancer

- Exposes service via cloud provider’s load balancer 
- Layer 4 (TCP) 
- One load balancer per service 

### Ingress

- Requires Ingress Controller (e.g. NGINX) 
- Layer 7 (HTTP/HTTPS) 
- Allows: 
    - Multiple services behind a single IP 
    - Host-based / path-based routing 
    - TLS termination 

### Use Cases:

- **LoadBalancer**: Simple, single-service exposure 
- **Ingress**: Complex routing, multiple services, TLS

References: [[Kubernetes Course Notes]]