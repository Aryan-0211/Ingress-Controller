README.md
# Ingress Controller Project

This repository contains configurations for setting up an **Ingress Controller** using **Nginx** within a **Kubernetes** cluster, leveraging **Minikube** for local development.

## Project Overview

This project aims to demonstrate how to deploy an Nginx Ingress Controller and configure Ingress resources for routing traffic to different services. The setup includes:

- Deploying the Nginx Ingress Controller using Kubernetes `Deployment`.
- Exposing the Nginx Ingress Controller using a `NodePort` service.
- Configuring Ingress resources for routing traffic to the `wear-service` and `watch-service` on specific paths (`/wear` and `/watch`).

## Key Features

- **Ingress Controller Deployment**: Uses Nginx for handling HTTP(S) traffic and routing requests to backend services.
- **NodePort Service**: Exposes the Nginx Ingress Controller outside the cluster using static ports on all nodes.
- **Ingress Resources**: Configures paths for routing traffic to backend services such as `wear-service` and `watch-service`.
- **Minikube Integration**: Can be run on Minikube to simulate the setup in a local Kubernetes environment.

## Prerequisites

To get started, you need the following:

- [Minikube](https://minikube.sigs.k8s.io/docs/) installed on your local machine.
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed for interacting with Kubernetes.
- A running Kubernetes cluster (Minikube can be used to create a local cluster).
- Basic understanding of Kubernetes and Ingress resources.

## Setup Instructions

### 1. Start Minikube
Ensure Minikube is running:

```bash
minikube start
2. Apply the Kubernetes Resources
Clone this repository and apply the necessary YAML configurations to deploy the Ingress Controller and other services:

bash
Copy code
kubectl apply -f ingress_def.yaml
kubectl apply -f ingress_service.yaml
kubectl apply -f ingress_wear_watch.yaml
3. Expose the Service and Ingress
Once the resources are applied, expose the Nginx Ingress Controller service on specific ports using the NodePort type.

bash
Copy code
kubectl get svc nginx-ingress
This will show you the external IP and port you can access the services from.

4. Access the Services
Use Minikube's IP to access the services externally:

bash
Copy code
minikube ip
For the wear-service, visit:

php
Copy code
http://<minikube_ip>:<NodePort>
Similarly, for the watch-service:

php
Copy code
http://<minikube_ip>:<NodePort>/watch
5. Verify the Deployment
To check the status of the deployments and services:

bash
Copy code
kubectl get pods
kubectl get services
kubectl get ingress
License
This project is licensed under the MIT License - see the LICENSE file for details.

Contact
For any issues or questions, feel free to open an issue or reach out via email:

Email: aryangadhavi79@gmail.com
