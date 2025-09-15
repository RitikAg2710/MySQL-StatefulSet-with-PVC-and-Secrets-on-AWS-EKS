# MySQL-StatefulSet-with-PVC-and-Secrets-on-AWS-EKS

Samajh gaya bhai ⚡ tu chaahta hai sirf ek **clean README.md** file jo GitHub pe project explain kare, aur `.yaml` files ko repo me manually rakh lega.

Yeh ready-to-use README copy kar le aur `README.md` file bana ke repo me daal de:

---

# 🚀 MySQL StatefulSet with PVC and Secrets on AWS EKS

## 📌 Overview

This project demonstrates how to deploy a **stateful MySQL database** on **AWS EKS (Elastic Kubernetes Service)** using:

* **Secrets** → Securely store MySQL root password
* **Persistent Volume Claim (PVC)** → Provision AWS EBS for data persistence
* **StatefulSet** → Ensure stable pod identity and persistent storage
* **ClusterIP/Headless Service** → Enable internal access to the MySQL database

---

## 🏗️ Architecture

1. **AWS EKS cluster** (worker nodes = EC2 instances)
2. **MySQL StatefulSet pod** running inside Kubernetes
3. **AWS EBS volume** provisioned automatically via PVC
4. **Secrets** for secure DB credentials
5. **ClusterIP/Headless Service** for internal access

---

## 🔧 Technologies Used

* **AWS EKS** – Managed Kubernetes service
* **Kubernetes** – Container orchestration
* **MySQL** – Relational database
* **EBS (Elastic Block Store)** – Persistent storage
* **Secrets & ConfigMaps** – Secure credentials management

---

## 📂 Project Files

* `mysql-secret.yaml` → Stores MySQL root password securely
* `mysql-pvc.yaml` → Defines Persistent Volume Claim (PVC)
* `mysql-statefulset.yaml` → Deploys MySQL as a StatefulSet
* `mysql-service.yaml` → Exposes MySQL via ClusterIP/Headless Service

---

## 🚀 Deployment Steps

### 1️⃣ Create Secret

```bash
kubectl apply -f mysql-secret.yaml
```

### 2️⃣ Create PVC

```bash
kubectl apply -f mysql-pvc.yaml
```

### 3️⃣ Deploy StatefulSet

```bash
kubectl apply -f mysql-statefulset.yaml
```

### 4️⃣ Create Service

```bash
kubectl apply -f mysql-service.yaml
```

---

## ✅ Verification

Check pods:

```bash
kubectl get pods
```

Check PVC binding:

```bash
kubectl get pvc
```

Check service:

```bash
kubectl get svc
```

---

## 🧹 Cleanup

Delete resources:

```bash
kubectl delete -f mysql-secret.yaml
kubectl delete -f mysql-pvc.yaml
kubectl delete -f mysql-statefulset.yaml
kubectl delete -f mysql-service.yaml
```

Delete cluster (to avoid AWS charges):

```bash
eksctl delete cluster --name mysql-eks-cluster --region ap-south-1
```

---

## 📖 Key Learnings

* Kubernetes **StatefulSet** is used for stateful apps like databases
* **PVC + EBS** ensure data persistence even if pods restart
* **Secrets** securely manage credentials
* **ClusterIP/Headless Service** enables stable access inside cluster

---


