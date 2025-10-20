# Kubernetes Pricing Algorithm Deployment

This repository contains Kubernetes manifests to deploy a **Pricing Algorithm** for various resources. Each resource has its own deployment manifest and exposes an HTTP endpoint on the node for querying the current pricing.

---

## Resource Manifests

| Resource | Manifest File       | Port |
|----------|------------------|------|
| vCPU     | `vcpu_price.yaml`   | 8083 |
| vGPU     | `vgpu_price.yaml`   | 8082 |
| RAM      | `ram_price.yaml`    | 8081 |
| Storage  | `storage_price.yaml`| 8084 |

---

## Deployment Instructions

1. **Apply all manifests**

```bash
kubectl apply -f vcpu_price.yaml
kubectl apply -f vgpu_price.yaml
kubectl apply -f ram_price.yaml
kubectl apply -f storage_price.yaml

2. **Query the Pricing API**

curl http://<NodeIP>:8081   # RAM
curl http://<NodeIP>:8082   # vGPU
curl http://<NodeIP>:8083   # vCPU
curl http://<NodeIP>:8084   # Storage

