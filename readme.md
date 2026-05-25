# 🚀 Minikube Kubernetes Project

A hands-on Kubernetes project that demonstrates deploying, managing, and scaling containerized applications on a **local Kubernetes cluster** using **Minikube**, **Docker**, and **kubectl**.

📦 **Repository:** [mimikube_kubernetes_project](https://github.com/Tam55si/mimikube_kubernetes_project)

---

## 📌 Project Overview

This project provides a practical demonstration of core Kubernetes concepts by deploying containerized applications on a local Minikube cluster. It covers the complete workflow — from building Docker images to creating Kubernetes resources using declarative YAML manifests.

**Minikube** sets up a lightweight, single-node Kubernetes cluster locally, making it ideal for learning, development, and testing without the cost of cloud infrastructure.

---

## 🏗️ Architecture

```
┌─────────────────────┐
│   User / Browser    │
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│   Kubernetes        │
│   Service (NodePort)│
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│   Deployment        │
│   (ReplicaSet)      │
└────┬──────────┬─────┘
     │          │
     ▼          ▼
┌─────────┐ ┌─────────┐
│  Pod 1  │ │  Pod 2  │
│(Container)│(Container)│
└─────────┘ └─────────┘
```

---

## 🧰 Tech Stack

| Technology    | Purpose                                  |
|---------------|------------------------------------------|
| **Kubernetes**| Container orchestration platform         |
| **Minikube**  | Local single-node Kubernetes cluster     |
| **Docker**    | Containerization of applications         |
| **kubectl**   | Kubernetes CLI for managing resources    |
| **YAML**      | Declarative configuration manifests      |

---

## 📁 Project Structure

```
mimikube_kubernetes_project/
│
├── deployment.yaml          # Kubernetes Deployment manifest
├── service.yaml             # Kubernetes Service manifest
├── pod.yaml                 # Standalone Pod definition
├── namespace.yaml           # Namespace configuration
├── Dockerfile               # Docker image build instructions
├── app/                     # Application source code
│   └── ...
└── README.md                # Project documentation
```

> 💡 *Update this section based on the actual files in your repository.*

---

## ⚙️ Prerequisites

Ensure the following tools are installed on your machine:

- ✅ [**Minikube**](https://minikube.sigs.k8s.io/docs/start/) — Local Kubernetes cluster
- ✅ [**kubectl**](https://kubernetes.io/docs/tasks/tools/) — Kubernetes CLI
- ✅ [**Docker**](https://docs.docker.com/get-docker/) — Container runtime
- ✅ 2+ CPUs, 2GB+ RAM, 20GB+ free disk space

Verify installations:

```bash
minikube version
kubectl version --client
docker --version
```

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Tam55si/mimikube_kubernetes_project.git
cd mimikube_kubernetes_project
```

### 2️⃣ Start Minikube Cluster

```bash
minikube start --driver=docker
```

Verify the cluster is running:

```bash
minikube status
kubectl get nodes
```

### 3️⃣ Build Docker Image (if applicable)

Point Docker to Minikube's Docker daemon and build the image:

```bash
eval $(minikube docker-env)
docker build -t my-app:latest .
```

---

## 📦 Deploy to Kubernetes

### Apply Namespace (if applicable)

```bash
kubectl apply -f namespace.yaml
```

### Apply Deployment

```bash
kubectl apply -f deployment.yaml
```

### Apply Service

```bash
kubectl apply -f service.yaml
```

### Verify Resources

```bash
kubectl get all
```

---

## 🌐 Access the Application

Use Minikube to expose and access the service:

```bash
minikube service <service-name>
```

Or use port forwarding:

```bash
kubectl port-forward service/<service-name> 8080:80
```

Then visit: **http://localhost:8080**

---

## 🔍 Useful kubectl Commands

| Command                              | Description                          |
|--------------------------------------|--------------------------------------|
| `kubectl get pods`                   | List all pods                        |
| `kubectl get services`              | List all services                    |
| `kubectl get deployments`           | List all deployments                 |
| `kubectl describe pod <pod-name>`    | Detailed info about a pod            |
| `kubectl logs <pod-name>`            | View pod logs                        |
| `kubectl exec -it <pod-name> -- sh` | Open shell inside a container        |
| `kubectl delete -f <file.yaml>`      | Delete a resource                    |
| `kubectl get all -n <namespace>`     | List all resources in a namespace    |
| `minikube dashboard`                 | Open Kubernetes Dashboard in browser |

---

## 📚 Key Kubernetes Concepts Covered

| Concept         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| **Pod**         | Smallest deployable unit; wraps one or more containers                      |
| **Deployment**  | Manages ReplicaSets; ensures desired number of pods are running             |
| **Service**     | Exposes pods to network traffic (ClusterIP, NodePort, LoadBalancer)         |
| **ReplicaSet**  | Ensures a specified number of identical pod replicas are running            |
| **Namespace**   | Logical isolation of resources within a cluster                             |
| **kubectl**     | CLI tool to interact with the Kubernetes API server                         |
| **Minikube**    | Tool to run a single-node Kubernetes cluster locally                        |

---

## 🧹 Clean Up

Stop and delete the Minikube cluster:

```bash
# Delete deployed resources
kubectl delete -f service.yaml
kubectl delete -f deployment.yaml

# Stop Minikube
minikube stop

# Delete the cluster entirely
minikube delete
```

---

## ⚠️ Troubleshooting

| Issue                          | Solution                                              |
|--------------------------------|-------------------------------------------------------|
| Pods stuck in `Pending`        | Check resources: `kubectl describe pod <pod-name>`    |
| ImagePullBackOff               | Ensure Docker image is built in Minikube's Docker env |
| Service not accessible         | Run `minikube service list` to check endpoints        |
| Minikube won't start           | Try `minikube delete` and `minikube start` again      |
| kubectl connection refused     | Ensure Minikube is running: `minikube status`         |

---

## 🎯 Future Improvements

- 🔀 **Ingress Controller** — Route external traffic with custom rules
- 🔄 **CI/CD Pipeline** — Automate build & deploy with GitHub Actions
- 🔐 **ConfigMaps & Secrets** — Manage environment variables securely
- 📈 **Horizontal Pod Autoscaler (HPA)** — Auto-scale based on load
- 📊 **Monitoring** — Integrate Prometheus & Grafana for observability
- 💾 **Persistent Volumes** — Add stateful storage for databases

---

## 👤 Author

**Tanmoy Si**
- 🔗 GitHub: [@Tam55si](https://github.com/Tam55si)
- 🔗 LinkedIn: [Tanmoy Si](https://www.linkedin.com/in/tanmoy-si-1a2329b4)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

---

⭐ **If you found this project helpful, please consider giving it a star!**
