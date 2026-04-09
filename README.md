Project Title

CI/CD Pipeline with Docker & AWS Deployment

Project Overview

This project demonstrates a complete DevOps CI/CD pipeline that automatically builds, containerizes, and deploys a Node.js application using GitHub Actions, Docker, and AWS EC2.

CI/CD Workflow

 Steps Automated:
Code pushed to GitHub
GitHub Actions triggers pipeline
Install dependencies & build app
Build Docker image
Push image to Docker Hub
SSH into AWS EC2
Pull latest Docker image
Run container and deploy app


Step-by-Step CI/CD Process (Explanation)

Step 1: Code Development

The developer writes the Node.js application code and pushes it to a GitHub repository.

Step 2: Code Push to GitHub

Every time code is pushed to the main branch, GitHub detects the change and triggers the CI/CD pipeline using GitHub Actions.

Step 3: GitHub Actions Trigger

GitHub Actions automatically starts the workflow defined in the .github/workflows file. It sets up a virtual machine (runner) to execute all steps.

Step 4: Install Dependencies & Build

Inside the runner:

Node.js environment is set up
Dependencies are installed (npm install)
Application is prepared for deployment
Step 5: Docker Image Creation

A Docker image is built using the Dockerfile, which packages the Node.js application along with all required dependencies into a container.

Step 6: Push Image to Docker Hub

The newly created Docker image is:

Tagged with a version or latest
Pushed to Docker Hub (container registry)
Step 7: Connect to AWS EC2

The pipeline connects to an AWS EC2 instance using SSH credentials stored in GitHub Secrets.

Step 8: Deploy on EC2

On the EC2 server:

Latest Docker image is pulled from Docker Hub
Old container (if running) is stopped
New container is started using the updated image
Step 9: Application Goes Live

The Node.js application runs inside a Docker container on EC2 and is accessible publicly via:

http://<EC2-public-ip>:3000
Step 10: Continuous Automation

Every new code push repeats this entire process automatically, ensuring continuous integration and continuous deployment without manual work
