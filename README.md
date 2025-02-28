
# Helm Charts Repository

This repository contains Helm charts for deploying applications on Kubernetes. The available chart:

- **E-Commerce Node.js App Helm Chart**

## 📌 Prerequisites

Before using this chart, ensure you have:

- A running **Kubernetes cluster** (Minikube, EKS, AKS, GKE, etc.)
- [Helm](https://helm.sh/docs/intro/install/) installed
- Docker and Kubernetes CLI installed
- Access to a container registry (DockerHub, ECR, ACR, GCR, etc.)

---

## 📥 Adding the Helm Repository

To use the charts from this repository, add it to your Helm client:

```sh
helm repo add my-repo https://lily4499.github.io/helm-charts
helm repo update

To verify the repository:
helm search repo my-repo

You should see the available charts listed.

📦 Installing the E-Commerce Node.js App Chart

To deploy the application using the Helm chart:
helm install ecommerce-app my-repo/ecommerce-node-app-chart --version 0.1.0

If you need to override values, create a values.yaml file and install it with:
helm install ecommerce-app -f my-values.yaml my-repo/ecommerce-node-app-chart --version 0.1.0

🛠 Verifying Deployment

Check if the release is deployed:
helm repo list
helm list

Check Kubernetes resources:
kubectl get pods,svc,deploy

🔄 Upgrading the Chart
If the chart is updated and you need to apply changes:
helm upgrade ecommerce-app my-repo/ecommerce-node-app-chart --version 0.1.0

❌ Uninstalling the Chart
helm uninstall ecommerce-app

🌍 Exposing the Application
To check the service and access the application:
kubectl get svc ecommerce-app -o wide


For port-forwarding (if using ClusterIP):
kubectl port-forward svc/ecommerce-app 8080:80

🔍 Debugging
Check logs:
kubectl logs -l app=ecommerce-app

Describe pods for troubleshooting:
kubectl describe pod -l app=ecommerce-app

⚙ Customizing Deployment
Modify values.yaml to configure:

Replica count
Image repository and tag
Service type (ClusterIP, NodePort, LoadBalancer)
Ingress settings
Environment variables

Example:

replicaCount: 2

image:
  repository: my-dockerhub-user/ecommerce-node-app
  tag: latest
  pullPolicy: IfNotPresent

service:
  type: LoadBalancer
  port: 80
  targetPort: 3000


📜 License
This repository and its charts are licensed under the MIT License.



