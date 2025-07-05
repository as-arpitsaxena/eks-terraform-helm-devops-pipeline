# eks-terraform-helm-devops-pipeline
End-to-end CI/CD pipeline using terraform, jenkins,helm on AWS EKS
EKS DevOps Pipeline with Terraform, Jenkins, Helm, and Prometheus

A complete DevOps CI/CD pipeline project that:
- Provisions AWS EKS infrastructure using Terraform
- Deploys a sample NGINX app via Jenkins + Helm
- Monitors using Prometheus + Grafana

---

## 🧱 Tools Used

| Tool        | Purpose                      |
|-------------|-------------------------------|
| *Terraform*  | AWS infrastructure (VPC, EKS) |
| *AWS EKS*    | Kubernetes cluster           |
| *Jenkins*    | CI/CD pipeline               |
| *Docker*     | Containerize the app         |
| *Helm*       | Kubernetes deployment        |
| *Prometheus* | Monitoring                   |
| *Grafana*    | Dashboards & visualization   |

## ⚙️ What It Does

1. *Terraform* provisions:
   - AWS VPC
   - EKS Cluster
   - Subnets + IAM roles

2. *Jenkins Pipeline*:
   - Pulls app code from GitHub
   - Builds Docker image
   - Pushes to Docker Hub (your-dockerhub-username/nginx)
   - Deploys to EKS via Helm

3. *Helm* deploys:
   - A simple NGINX app with replicaCount = 2

4. *Prometheus + Grafana*:
   - Monitors CPU, memory, pod health
   - Grafana dashboards available on port 3000

---

## 🛠️ How to Run This Project

### Prerequisites:
- AWS CLI configured
- kubectl + helm + terraform + docker installed
- Jenkins setup (or use Jenkins in Docker or on EKS)
- DockerHub account

### Terraform Setup:

```bash
cd terraform
terraform init

terraform/          -> EKS infrastructure code
jenkins/            -> CI/CD pipeline
helm/sample-app-chart/  -> Helm chart for app
README.md           -> Project info (this file)
terraform apply
