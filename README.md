# CI-CD-Pipeline-
Project-1

This project demonstrates a complete CI/CD pipeline using GitHub Actions, Docker, Docker Hub, and Minikube to deploy a simple Flask web application. Everything is automated from build to deploy — without using a public cloud provider.


✅ Prerequisites

Before you begin, make sure you have:
    Docker - installed and running
    A Docker Hub account
    Minikube -  for local Kubernetes
    Kubectl
    GitHub Account

1. Clone the Repository

        git clone https://github.com/AshfaqShah786/CI-CD-Pipeline-.git
        cd CI-CD-Pipeline-


2. Run the App Locally (Optional Test)


         docker-compose up --build

3. Create a Docker Image and Push to Docker Hub

Login to Docker:

        docker login

Build and tag the image:

        docker build -t ashfaqs96/ci-cd-pipeline:latest .
    
Push the image:

        docker push ashfaqs96/ci-cd-pipeline:latest

4. GitHub Actions: Automate CI/CD

            Add GitHub Secrets:
            Go to your GitHub repo → Settings → Secrets and variables → Actions → New repository secret.
            DOCKER_USERNAME = your Docker Hub username
            DOCKER_PASSWORD = your Docker Hub password

5. Run Locally with Minikube (Kubernetes)

Start Minikube:

        minikube start
    
Create Deployment:

        kubectl create deployment myapp --image=ashfaqs96/ci-cd-pipeline:latest

Expose as a NodePort Service:

        kubectl expose deployment myapp --type=NodePort --port=5000

Access the Service:

        minikube service myapp


🔗 This will open the app in your default browser.
