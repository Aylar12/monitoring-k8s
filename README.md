# 📊 Kubernetes Monitoring Stack (Helm-based)

A complete Kubernetes Monitoring Stack built using Helm, including:

Prometheus – metrics collection & alerting

Grafana – visualization & dashboards (auto-provisioned)

Loki – log aggregation

Grafana Alloy – metrics & logs agent


This project demonstrates a production-like monitoring setup deployed fully via Helm charts.


---

## 🧱 Architecture Overview
```text
Kubernetes Cluster
│
├── Prometheus  ← Metrics & Alerts
│
├── Grafana     ← Dashboards (Provisioned)
│
├── Loki        ← Logs
│
└── Alloy       ← Metrics + Logs Agent
```

---

## 🚀 Features

✅ Helm-based deployment

✅ Auto-provisioned Grafana dashboards

✅ Auto-provisioned Grafana datasources

✅ Prometheus alert rules via ConfigMap

✅ Centralized logs with Loki

✅ Clean Kubernetes-native configuration

✅ Ready for extension (Email alerts, Slack, etc.)



---

## 📁 Project Structure
```text
monitoring-k8s/
├── helm/
│   └── monitoring/
│       ├── Chart.yaml
│       ├── values.yaml
│       └── templates/
│           ├── namespace.yml
│           ├── alloy/
│           │   ├── alloy-deployment.yml
│           │   ├── alloy-service.yml
│           │   └── alloy-configmap.yml
│           ├── prometheus/
│           │   ├── prometheus-deployment.yml
│           │   ├── prometheus-service.yml
│           │   ├── prometheus-configmap.yml
│           │   └── configmap-alerts.yml
│           ├── grafana/
│           │   ├── grafana-deployment.yml
│           │   ├── grafana-service.yml
│           │   ├── datasources-provisioning-configmap.yml
│           │   ├── dashboards-provisioning-configmap.yml
│           │   └── configmap-dashboards.yml
│           └── loki/
│               ├── loki-deployment.yml
│               ├── loki-service.yml
│               └── loki-configmap.yml
│
├── dashboard-image
│    └── Screenshot.png
│
└── README.md
```

---

## ⚙️ Prerequisites

Kubernetes cluster (Kind / Minikube / K3s)

kubectl

Helm v3+



---

## 🛠️ Installation

### 1️⃣ Clone repository
```bash
git clone https://github.com/<your-username>/monitoring-k8s.git
cd monitoring-k8s
```

---

### 2️⃣ Install Helm chart
```bash
helm install monitoring ./helm/monitoring
```

---

### 3️⃣ Verify pods
```bash
kubectl get pods -n monitoring
```
Expected output:

alloy        Running
grafana      Running
loki         Running
prometheus   Running


---

## 🌐 Access Services

Grafana
```bash
kubectl port-forward -n monitoring svc/grafana 3000:3000
```
➡️ http://localhost:3000
Username: admin
Password: admin


---

## Prometheus
```bash
kubectl port-forward -n monitoring svc/prometheus 9090:9090
```
➡️ http://localhost:9090


---

## 📸 Screenshots

Grafana Dashboards

> 📍 Add your Grafana dashboard screenshot here



![Grafana Dashboard](/dashboard-image/Screenshot.png)


---


## 🚨 Alerts

Example alert rules:

Instance down

High CPU usage


Alerts are managed via:

templates/prometheus/configmap-alerts.yml

Ready for extension with:

Email

Slack

Alertmanager integration



---

## 📈 Metrics & Logs

Metrics collected via Prometheus & Alloy

Logs collected via Alloy → Loki

Visualization via Grafana



---

## 🧠 What This Project Demonstrates

Helm chart design

Kubernetes ConfigMaps & Deployments

Monitoring best practices

Production-ready observability stack

Real-world DevOps skills



---

## 🔮 Future Improvements

Alertmanager integration

Email / Slack notifications

TLS & authentication

Multi-environment Helm values

CI/CD pipeline



---

## 👤 Author

Aylar
Computer Engineer | DevOps & Monitoring Enthusiast


