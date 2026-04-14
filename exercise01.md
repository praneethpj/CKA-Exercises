# ⚙️ Kubernetes Commands – Pod Creation

## 📌 Objective

Generate a Pod YAML file using `kubectl` and apply it to the cluster.

---

## 🧾 Commands

### 🔹 1. Generate Pod YAML (Dry Run)

```bash
kubectl run web \
  --image=nginx:1.27 \
  -n exercise-01 \
  --dry-run=client \
  -o yaml > webpod.yaml
```

### 🔹 2. Create Pod

```bash
kubectl create -f webpod.yaml
```

### 🔹 3. Verify

```bash
kubectl get pod web -n exercise-01
```

### 🔹 3. Cleanup

```bash
kubectl delete pod/web -n exercise-01
kubectl delete ns exercise-01
```
