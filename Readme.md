# Kubernetes_chatbot 

A Kubernetes infrastructure project that deploys a chatbot application using Kubernetes manifests. This repository provides everything needed to run a chatbot (API + UI) in a Kubernetes cluster (like Minikube or any Kubernetes environment).

---

## Project Purpose

This project automates the deployment of a chatbot and its services on a Kubernetes cluster. It includes workload definitions, service exposure, secrets, config maps, and ingress so you can run and scale the chatbot in cloud‑native environments such as Minikube, Docker Desktop Kubernetes, or any managed Kubernetes service.

---

## Project Structure

```

Kubernetes_chatbot/
├─ chatbot-api-deployment.yml      # Deployment manifest for chatbot backend
├─ chatbot-api-service.yml         # Service manifest for backend API
├─ chatbot-ihm-deployment.yml      # Deployment manifest for chatbot frontend (UI)
├─ chatbot-ihm-service.yml         # Service manifest for frontend
├─ chatbot-secrets.yml             # Kubernetes Secret definitions
├─ chatbot_configmap.yml           # ConfigMap for environment variables
├─ ingress-chatbot.yml             # Ingress manifest for external access
├─ namespace.yml                   # Namespace definition for isolation
├─ kustomization.yml               # Kustomize config to build all resources
├─ Minikube‑linux‑amd64           # Minikube binary (optional utility)
├─ README.md
└─ .gitignore

````

---

## Prerequisites

To deploy this project you need:

- A Kubernetes cluster (e.g., **Minikube**)
- **kubectl** CLI configured for your cluster
- (Optional) An **Ingress Controller** installed for managing HTTP access

---

## Local Deployment (Minikube Example)

### 1. Start Minikube

```bash
minikube start
````

### 2. Apply the Kubernetes Resources

With all manifests in the root directory:

```bash
kubectl apply -k ./
```

This creates the namespace, deployments, services, ingress, secrets, and config needed to run the chatbot.

### 3. Access the Chatbot

If using Minikube with Ingress:

```bash
minikube tunnel
```

Then open a browser to the address configured in your `ingress-chatbot.yml` (e.g., `http://chatbot.local` if your DNS/hosts is configured accordingly). If not using Ingress, access via NodePort or service port:

```bash
kubectl get svc -n chatbot
```

---

## Features

* **Kubernetes manifests** for backend, frontend, services, ingress, secrets, and config
* **Namespace isolation** for cluster resources
* **Ingress & services** for external access
* Works with **Minikube** and other Kubernetes distributions

---

## Feedback & Contributions

* **Report issues:** Open a GitHub issue for bugs or suggestions
* **Contribute:** Fork the repository and submit a pull request
* **Contact:** Reach out via GitHub for questions or collaboration

