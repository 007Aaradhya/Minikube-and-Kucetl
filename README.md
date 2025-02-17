# Minikube and kubectl Setup

## Overview
This experiment demonstrates how to set up Minikube and use kubectl to deploy and manage an Nginx service.

## Prerequisites
- Docker installed and running
- Minikube installed
- kubectl installed
- Git installed (for version control)

## Steps

### 1. Start Minikube
```bash
minikube start
```

### 2. Deploy an Nginx Pod
```bash
kubectl create deployment nginx --image=nginx
```

### 3. Expose the Nginx Service
```bash
kubectl expose deployment nginx --type=NodePort --port=80
```

### 4. Get the Service URL
```bash
minikube service nginx --url
```
Example Output:
```
http://127.0.0.1:64733
```

### 5. Verify Running Pods
```bash
kubectl get pods
```

### 6. Verify Running Services
```bash
kubectl get svc
```

## Troubleshooting
### If the Service Is Not Accessible:
- Check if the pod is still creating:
  ```bash
  kubectl get pods
  ```
  If `STATUS` is `ContainerCreating`, wait for it to start.

- If Minikube service fails:
  ```bash
  minikube logs --file=logs.txt
  ```
  Attach `logs.txt` to an issue if needed.

## GitHub Repository Setup

### Initialize Git Repository
```bash
git init
git branch -M main
git remote add origin https://github.com/007Aaradhya/Minikube-and-Kubectl.git
```

### Add and Commit Files
```bash
touch README.md
echo "# Minikube and kubectl Setup" > README.md
git add .
git commit -m "Initial commit"
```

### Push to GitHub
```bash
git push -u origin main
```

## Conclusion
This experiment helps understand the deployment of a simple Nginx service using Minikube and kubectl. If any issues arise, check logs and ensure Minikube is running correctly.

