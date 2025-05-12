# 🏗️ Infraestructura - Construtem

Este repositorio contiene la configuración de infraestructura del sistema **Construtem**, una ferretería digital basada en arquitectura de microservicios. Aquí se gestiona la contenerización y orquestación de los servicios utilizando Docker, Kubernetes y Google Kubernetes Engine (GKE).

## ⚙️ Tecnologías utilizadas

- **Docker**: Contenerización de microservicios.
- **Kubernetes (K8s)**: Orquestación de contenedores.
- **GKE (Google Kubernetes Engine)**: Cluster gestionado para producción.
- **GitHub Actions**: Automatización del pipeline de CI/CD.

## 📁 Estructura del repositorio

```
infra/
├── docker/
├── k8s/
│   ├── deployments/
│   ├── services/
│   └── ingress/
└── ci-cd/
```

## 🐳 Docker

### Subir imagen a Google Container Registry (GCR)

```bash
docker tag backend-ventas gcr.io/<PROJECT_ID>/backend-ventas
docker push gcr.io/<PROJECT_ID>/backend-ventas
```

## ☸️ Kubernetes en GKE

### 1. Crear el cluster

```bash
gcloud container clusters create construtem-cluster   --num-nodes=3   --zone=us-central1-a   --enable-ip-alias
```

### 2. Obtener credenciales

```bash
gcloud container clusters get-credentials construtem-cluster --zone=us-central1-a
```

### 3. Desplegar recursos

```bash
kubectl apply -f k8s/deployments/
kubectl apply -f k8s/services/
kubectl apply -f k8s/ingress/
```

## ✅ Requisitos

- Docker
- kubectl
- gcloud CLI
