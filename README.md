# kubernetes_hello_world

This project demonstrates a basic setup for a Node.js application with Docker and Kubernetes deployment.

## 1. Create an App

```bash
npm install
npm start
```

## 2. Create a Docker Container

```bash
# docker build -t my-node-app .
# docker build -t docker/my-node-app -f docker/Dockerfile .
docker build -t my-node-app -f docker/Dockerfile .
docker tag my-node-app cesarchamal/my-node-app
docker push cesarchamal/my-node-app
# If you want to push a specific version, e.g., 'first', use:
# docker push cesarchamal/my-node-app:first
```

## 3. Create a Kubernetes Deployment

```bash
kubectl apply -f config/deployment.yaml
kubectl get pods
kubectl logs my-node-app-service
kubectl delete pod my-node-app-deployment-5c6c969df6-67b54 my-node-app-deployment-857f55d67f-n8dt8
kubectl delete pods -l app=my-node-app
```

## 4. Expose Your Application

```bash
kubectl apply -f config/service.yaml
kubectl get service my-node-app-service
kubectl describe service my-node-app-service
kubectl get services
kubectl get svc
kubectl delete service my-node-app-service
```

## 5. Access Your Application

```bash
curl http://localhost:8080
```