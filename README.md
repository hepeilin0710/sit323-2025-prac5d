# sit323-2025-prac5d

# Dockerised Calculator Microservice - Google Cloud Deployment

This project is a Node.js-based calculator microservice that supports basic math operations via HTTP POST requests. The microservice is containerised using Docker, and the final image is uploaded to Google Cloud's private container registry (Artifact Registry).

## Google Cloud Container Registry Setup

### 1. Project and Repository Setup

- **GCP Project ID:** `sit323-25t1-peilin-he-4af9d68`
- **Artifact Registry Name:** `sit323`
- **Location:** `australia-southeast2` (Melbourne)
- **Format:** Docker


---

## Docker Image Build and Push Instructions

### Step 1: Set the active GCP project

```
gcloud config set project sit323-25t1-peilin-he-4af9d68
Step 2: Authenticate Docker with Artifact Registry
bash

gcloud auth configure-docker australia-southeast2-docker.pkg.dev
Step 3: Tag the local Docker image
Replace my-web-app with your local image name (built from Dockerfile).


docker tag my-web-app australia-southeast2-docker.pkg.dev/sit323-25t1-peilin-he-4af9d68/sit323/calculator-app:v1
Step 4: Push the image to Artifact Registry

docker push australia-southeast2-docker.pkg.dev/sit323-25t1-peilin-he-4af9d68/sit323/calculator-app:v1
Step 5: Run the image from the registry to test

docker run -p 3000:3000 australia-southeast2-docker.pkg.dev/sit323-25t1-peilin-he-4af9d68/sit323/calculator-app:v1
