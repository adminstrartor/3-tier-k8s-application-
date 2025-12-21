# 3-Tier Application Deployment on Kubernetes

This project demonstrates how to deploy a simple **3-tier application**
(Frontend, Backend, Database) on a Kubernetes cluster using Docker

## Architecture
The application follows a 3-tier architecture:

- **Frontend**: Nginx (Static UI)
- **Backend**: Python Flask API
- **Database**: MySQL

Frontend → Backend → Database

## Objective
To deploy a three-tier application on Kubernetes using Docker images
for frontend and backend, and MySQL as the database.

## Components
- Frontend: Dockerized UI
- Backend: Dockerized API
- Database: MySQL deployed locally in Kubernetes

## Tools Used
- Docker
- Kubernetes (kubeadm cluster)
- GitHub
## Project Structure
backend/
├── Dockerfile
├── app.py
└── requirements.txt

frontend/
├── Dockerfile
└── index.html

k8s/
├── backend-deployment.yaml
├── backend-service.yaml
├── frontend-deployment.yaml
├── frontend-service.yaml
├── mysql-deployment.yaml
└── mysql-service.yaml
## Build Docker Images
Build backend image
docker build -t backend:1.0 ./backend
Build frontend image:
docker build -t frontend:1.0 ./frontend
## Kubernetes Deployment
kubectl apply -f k8s/
Check pods:
kubectl get pods
check service
kubectl get svc
## Access Application
http://<NODE-IP>:30080
## Notes 
Kubernetes Services are used for internal communication.
Backend connects to MySQL using service name.
  
