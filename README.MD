This repository contains the Kubernetes configurations for deploying the bimbs-app application. The application is containerized and hosted on a private Docker registry.

Files
* deployment.yaml: Defines the deployment configuration for bimbs-app.
* service.yaml: Defines the service configuration to expose the application.
* ingress.yaml: Defines the ingress configuration for routing external traffic to the application.
===========
Deployment
Prerequisites
* Kubernetes cluster
* kubectl configured to interact with the cluster
* Docker registry credentials stored as a Kubernetes secret (regcred)
* NGINX Ingress Controller installed in the cluster
===========
Getting Started
Prerequisites
* Kubernetes cluster
* kubectl configured
* Docker registry credentials (for private images)

Deployment Steps
Create Secrets

Ensure you have the Docker registry credentials stored as a Kubernetes Secret named regcred:
kubectl create secret docker-registry regcred --docker-server=<DOCKER_REGISTRY_SERVER> --docker-username=<USERNAME> --docker-password=<PASSWORD> --docker-email=<EMAIL>

Deploy the Application
kubectl apply -f deployment.yaml

Expose the Service
kubectl apply -f service.yaml

Configure Ingress
kubectl apply -f ingress.yaml

Once the Ingress is set up, you can access the application at http://bimbs.dev/api/health.

