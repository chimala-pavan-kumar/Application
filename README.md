# Store Website Deployment using Docker & Kubernetes

## Project Overview

This project demonstrates how to containerize a static website using Docker and deploy it on a Kubernetes cluster. The website is based on the TemplateMo 625 Folio Slideshow template and is served using the Nginx web server.

The project covers the complete deployment workflow from creating a Docker image to running multiple replicas in Kubernetes.

---

## Technologies Used

- HTML5
- CSS3
- JavaScript
- Nginx
- Docker
- Docker Hub
- Kubernetes (K8s)
- kubectl

---

## Project Structure

```
exercise/
│
├── index.html
├── css/
├── js/
├── images/
├── fonts/
├── Dockerfile
├── deployment.yaml
├── service.yaml
└── README.md
```

---

## Features

- Static website hosted using Nginx
- Dockerized application
- Docker image pushed to Docker Hub
- Kubernetes Deployment with 4 replicas
- Kubernetes NodePort Service
- Load balancing across multiple Pods
- Self-healing using Kubernetes Deployment
- Easily scalable application

---

## Dockerfile

```dockerfile
FROM nginx:latest

COPY . /usr/share/nginx/html

EXPOSE 80
```

---

## Build Docker Image

```bash
docker build -t pavankumarchimala/exercise:1 .
```

---

## Verify Docker Image

```bash
docker images
```

---

## Run Docker Container

```bash
docker run -d -p 80:80 pavankumarchimala/exercise:1
```

Access the application:

```
http://<server-ip>
```

---

## Login to Docker Hub

```bash
docker login
```

---

## Push Docker Image

```bash
docker push pavankumarchimala/exercise:1
```

---

## Kubernetes Deployment

Create the deployment

```bash
kubectl apply -f deployment.yaml
```

Verify deployment

```bash
kubectl get deployments
```

Verify Pods

```bash
kubectl get pods
```

Expected output

```
4 Pods Running
```

---

## Kubernetes Service

Create the service

```bash
kubectl apply -f service.yaml
```

Verify Service

```bash
kubectl get svc
```

---

## Access the Application

```
http://<Node-IP>:<NodePort>
```
## Kubernetes Concepts Used

- Deployment
- ReplicaSets
- Pods
- Labels
- Selectors
- NodePort Service
- Scaling
- Self-Healing
- Load Balancing

---

## Docker Concepts Used

- Docker Images
- Docker Containers
- Dockerfile
- Image Build
- Port Mapping
- Docker Hub

---

## Workflow

```
Website Files
      │
      ▼
Dockerfile
      │
      ▼
Docker Build
      │
      ▼
Docker Image
      │
      ▼
Docker Hub
      │
      ▼
Kubernetes Deployment
      │
      ▼
4 Running Pods
      │
      ▼
NodePort Service
      │
      ▼
Users Access Website
```

---

## Learning Outcomes

By completing this project, you will learn:

- How Docker containerizes applications
- How Nginx serves a static website
- How to build Docker images
- How to push images to Docker Hub
- How Kubernetes Deployments work
- How ReplicaSets maintain the desired number of Pods
- How Services expose applications
- How Kubernetes performs load balancing
- How Kubernetes provides self-healing
- Basic Kubernetes application deployment
