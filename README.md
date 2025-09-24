Node.js CI/CD Pipeline with Jenkins

This repository demonstrates a basic Jenkins CI/CD pipeline for a Node.js web application. The pipeline automates build, test, Dockerize, and deploy processes whenever code is updated.

Although originally designed for Jenkins, the pipeline is also implemented using GitHub Actions, so it can run fully online without installing Jenkins locally.

Project Contents

index.js – Simple Node.js Express app.

test.js – Basic test to ensure functionality.

package.json – Defines scripts and dependencies.

Dockerfile – Builds a Docker image of the app.

Jenkinsfile – Defines pipeline stages for Jenkins.

.github/workflows/main.yml – GitHub Actions workflow replicating the Jenkins pipeline.

Steps to Run (Online via GitHub Actions)

Add DockerHub secrets in your GitHub repo:

DOCKER_USERNAME → your DockerHub username

DOCKER_PASSWORD → your DockerHub password or access token

Push changes to the main branch → workflow triggers automatically.

Check logs in the Actions tab of your GitHub repository.

Run Docker image locally (optional):

docker pull YOUR_DOCKER_USERNAME/jenkins-demo-app:latest
docker run -p 3000:3000 YOUR_DOCKER_USERNAME/jenkins-demo-app:latest

How the Jenkins Pipeline Works

Build – Install Node.js dependencies.

Test – Run tests to verify code correctness.

Docker Build – Build a Docker image of the app.

Deploy – Run the app in a container.

The pipeline is triggered automatically on every code commit when configured in Jenkins or via the GitHub Actions workflow.
