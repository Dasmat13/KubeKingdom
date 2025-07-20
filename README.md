# 🌌 KubeFlask

**KubeFlask** is a cloud-native Flask web application deployed using Docker, Kubernetes, and AWS EKS. It uses Terraform for infrastructure provisioning and is designed for scalability, portability, and production-readiness.

---

## 📁 Project Structure

```
KubeFlask/
├── app/                    # Flask application source code
│   ├── app.py
│   └── requirements.txt
├── Dockerfile              # Docker image definition
├── docker-compose.yml      # For optional local multi-container testing
├── k8s/                    # Kubernetes manifests
│   ├── deployment.yaml
│   └── service.yaml
├── terraform/              # Terraform config for AWS EKS
│   ├── main.tf
│   └── variables.tf
├── README.md
```

---

## ⚙️ Prerequisites

Make sure the following tools are installed:

- Docker
- kubectl
- AWS CLI v2
- Terraform
- eksctl (optional)
- An AWS account with necessary IAM permissions

---

## 🚀 Local Development

### Build and Run Docker:

```bash
docker build -t kube-flask .
docker run -p 5000:5000 kube-flask
```

### Local Kubernetes (Minikube):

```bash
minikube start
kubectl apply -f k8s/
minikube service flask-service
```

---

## ☁️ Deploy to AWS EKS

### 1. Provision EKS with Terraform:

```bash
cd terraform/
terraform init
terraform apply
```

### 2. Configure `kubectl`:

```bash
aws eks update-kubeconfig --region us-east-1 --name kubeshare
```

### 3. Deploy App to EKS:

```bash
cd k8s/
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get svc
```

---

## 🧪 Testing the App

Get the external IP or LoadBalancer URL using:

```bash
kubectl get svc
```

Open the app in your browser or use `curl` to test the endpoint.

---

## 🧹 Cleanup

To remove all Kubernetes resources:

```bash
kubectl delete -f k8s/
```

To destroy AWS infrastructure:

```bash
cd terraform/
terraform destroy
```

---

## 📄 License

MIT License © 2025 Dasmat
