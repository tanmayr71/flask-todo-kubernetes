# Flask Todo Application on Kubernetes

This repository hosts a Flask-based Todo application that utilizes MongoDB for data persistence, containerized using Docker, and orchestrated with Kubernetes. This application is designed as part of the Cloud Computing course assignment at New York University, under the guidance of Professor Sambit Sahu.

## Repository Structure

- **DockerFiles**: Includes Dockerfiles for building the Flask and MongoDB containers.
- **Kubernetes**: Contains all Kubernetes yaml files for deploying and managing the application.
- **Screenshots**: Screenshots documenting the functionality and setup.
- **Detailed Assignment Documentation.pdf**: Full documentation of the assignment and project setup.

## Features

- Create, update, delete, and list todo items.
- Fully containerized application stack for easy deployment.
- Kubernetes manifests for orchestrating services including load balancers, persistent volumes, and health checks.

## Getting Started

### Prerequisites

- Docker
- Kubernetes (Minikube for local testing and AWS EKS for deployment in a production-like environment)
- `kubectl` configured for your Kubernetes cluster
- Docker Hub account (for pushing images)

### Local Setup

1. **Clone the repository**
git clone https://github.com/tanmayr71/flask-todo-kubernetes
cd flask-todo-kubernetes

2. **Build and run the Docker containers**
docker-compose up --build

3. **Access the application**
- The application is available at `http://localhost:5001` or the configured port in docker-compose.yml.

### Deployment on Kubernetes

1. **Start Minikube**
minikube start

2. **Deploy the application to Minikube**
kubectl apply -f kubernetes/

3. **Access the application using the Minikube IP**
minikube service list

4. **Cleanup**
kubectl delete -f kubernetes/

### Deployment on AWS EKS

1. **Set up an EKS cluster and configure `kubectl`**
aws eks --region <region-name> update-kubeconfig --name <cluster-name>

2. **Deploy the application to EKS**
kubectl apply -f kubernetes/

3. **Access the application via the LoadBalancer endpoint**
kubectl get svc -o wide

## Testing

- The application includes both manual and automated tests to ensure functionality across updates and deployments.

## High Availability and Scaling

- Utilizes Kubernetes ReplicationControllers and Deployments to ensure high availability and scaling.

## Monitoring and Alerting

- Integrated with Prometheus for monitoring and Alertmanager for alerting to a designated Slack channel on application issues.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## Authors

- **Tanmay Anil Rathi**
- **Simardeep Singh Mehta**

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
