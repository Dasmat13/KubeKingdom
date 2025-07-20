# 🌌 KubeFlask - Flask App on Kubernetes with AWS EKS

**KubeFlask** is a production-grade deployment of a containerized Flask web application, using:

- Docker for containerization
- Kubernetes for orchestration
- AWS EKS (Elastic Kubernetes Service) for cloud-native deployment
- Terraform for infrastructure provisioning

---

## 🧱 Project Structure

KubeFlask/
├── app/ # Flask application code
│ ├── app.py
│ └── requirements.txt
├── Dockerfile # Build Flask app image
├── docker-compose.yml # (optional) for local testing
├── k8s/ # Kubernetes manifests
│ ├── deployment.yaml
│ └── service.yaml
├── terraform/ # Infrastructure-as-Code for AWS
│ ├── main.tf
│ └── variables.tf
├── README.md

yaml
Copy
Edit

---

## 🚀 Features

- RESTful API powered by Flask
- Containerized using Docker
- Kubernetes YAMLs for scalable deployment
- Terraform scripts to create AWS EKS cluster
- CI/CD-ready for GitHub Actions or Jenkins
- Deployable on Minikube, GKE, or AWS EKS

---

## ⚙️ Prerequisites

Ensure these tools are installed:

- [AWS CLI v2](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Terraform](https://developer.hashicorp.com/terraform/install)
- [Docker](https://docs.docker.com/get-docker/)
- [eksctl](https://eksctl.io/) *(optional)*

---

## 🐳 Docker Usage

### Build the Docker Image:

```bash
docker build -t kube-flask .
Run Locally:
bash
Copy
Edit
docker run -p 5000:5000 kube-flask
🧪 Test Locally with Minikube (Optional)
bash
Copy
Edit
minikube start
kubectl apply -f k8s/
minikube service flask-service
☁️ Deploy to AWS EKS
Step 1: Provision EKS Cluster (Terraform)
bash
Copy
Edit
cd terraform/
terraform init
terraform apply
Step 2: Update kubeconfig
bash
Copy
Edit
aws eks update-kubeconfig --region us-east-1 --name kubeshare
Step 3: Deploy Flask App to EKS
bash
Copy
Edit
cd k8s/
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl get svc
🧼 Teardown
Delete Kubernetes resources:
bash
Copy
Edit
kubectl delete -f k8s/
Destroy Infrastructure:
bash
Copy
Edit
cd terraform/
terraform destroy
📷 Screenshots
Add screenshots or GIFs of your running app, K8s dashboard, etc.

📄 License
MIT License © 2025 Dasmat

yaml
Copy
Edit
