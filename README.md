# ce12-k8-3-7
Deploy a simple Nginx application on Amazon Elastic Kubernetes Service using Kubernetes and expose it via an AWS LoadBalancer service.

# EKS Nginx Deployment

This project deploys a simple Nginx application on AWS EKS using Kubernetes manifests.

## Prerequisites
- AWS CLI configured
- kubectl installed
- Access to EKS cluster

## Run Steps

### 1. Connect to EKS cluster
```bash
aws eks update-kubeconfig --name shared-eks-cluster --region <your-region>
```

### 2. Deploy Nginx
```bash
kubectl apply -f nginx-deployment.yaml
```

### 3. Expose service
```bash
kubectl apply -f nginx-service.yaml
```

### 4. Add service account
```bash
kubectl apply -f service-account.yaml
```

### 5. Check resources
```bash
kubectl get pods -n <your-namespace>
kubectl get svc -n <your-namespace>
```

### 6. Access app
```bash
kubectl get svc -n <your-namespace>
```

Then open the LoadBalancer DNS in browser.