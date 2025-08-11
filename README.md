# kubernetes-local-deployment
# 🚀 Kubernetes Deployment with Minikube (Windows)

## 📋 Objective
Deploy and manage a sample NGINX application using Kubernetes locally with Minikube on Windows.

---

## 🛠 Tools Used
- **Minikube** – Local Kubernetes cluster
- **kubectl** – Kubernetes CLI
- **Docker Desktop** – Container runtime
- **Windows PowerShell** – Command execution

---

## 📂 Files Included
- `deployment.yaml` – Defines the NGINX deployment with 2 replicas
- `service.yaml` – Exposes the deployment via NodePort
- `5_pods_and_services.png` – Screenshot showing running pods and services

---

## 📸 Screenshot Overview

### ✅ Pods and Services
![Pods and Services](5_pods_and_services.png)

- Two pods from `nginx-deployment` are running and healthy (`READY: 1/1`, `STATUS: Running`)
- NodePort service `nginx-service` is exposed on port `31459`
- App accessible via: `http://<minikube-ip>:31459`

---

## 📦 Deployment Summary

### 1. Start Minikube

minikube start --driver=docker
kubectl config use-context minikube

## Apply Deployment
kubectl apply -f deployment.yaml
kubectl get pods

## Apply Service
kubectl apply -f service.yaml
kubectl get svc

## Access App
minikube service nginx-service --http://127.0.0.1:51694/
----

## Scale Deployment
kubectl scale deployment nginx-deployment --replicas=4

## View Logs & Describe
kubectl describe pod <pod-name>
kubectl logs <pod-name>

