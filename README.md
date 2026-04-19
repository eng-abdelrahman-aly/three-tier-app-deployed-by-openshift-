# Three-Tier App Deployed by OpenShift

A full-stack application architecture consisting of a Node.js backend and an Nginx-based frontend, optimized for containerized deployment and automated orchestration on **OpenShift Container Platform**.

## 🏗 Project Structure

```text
.
├── backend/
│   ├── app.js              # Node.js Express API
│   ├── Dockerfile          # Backend container image definition
│   └── package.json        # Backend dependencies & metadata
├── frontend/
│   ├── index.html          # Web frontend entry point
│   ├── default.conf        # Nginx web server configuration
│   └── Dockerfile          # Frontend container image definition
├── build-be.yaml           # OpenShift Build Configuration for Backend
├── build-fe.yaml           # OpenShift Build Configuration for Frontend
└── buzzel-full-stack.yaml  # Deployment, Service, and Route orchestration

🚀 Deployment Guide

This project is designed to leverage OpenShift's native BuildConfigs and DeploymentConfigs to automate the path from code to production.
1. Prerequisites

    A running OpenShift cluster (e.g., CRC, Red Hat OpenShift Service on AWS).

    oc CLI tool authenticated to your cluster (oc login).

2. Deployment Steps

Apply the manifest files to your OpenShift namespace to initialize the infrastructure:
Bash

# Step 1: Create the Build resources (ImageStreams and BuildConfigs)
oc apply -f build-be.yaml
oc apply -f build-fe.yaml

# Step 2: Deploy the Full Stack (Deployments, Services, and Routes)
oc apply -f buzzel-full-stack.yaml

3. Triggering Builds

If your BuildConfigs are set up for Docker builds, trigger them manually with:
Bash

oc start-build backend-build-name --from-dir=./backend
oc start-build frontend-build-name --from-dir=./frontend

🛠 Tech Stack

    Frontend: HTML5, Nginx (Web Server)

    Backend: Node.js, Express (API)

    Orchestration: OpenShift / Kubernetes

    CI/CD: OpenShift Source-to-Image (S2I) & Build Pipelines

📝 Key Features

    Scalability: Separate frontend and backend tiers allow for independent horizontal scaling.

    OpenShift Native: Implements Routes for external DNS mapping and Services for internal load balancing.

    Configuration Management: Environment-ready deployment files for rapid environment replication.

Created by eng-abdelrahman-aly


### To apply this to your repo:
1. Run `nano README.md` in your terminal.
2. Paste the block above.
3. Save and exit (`Ctrl+O`, `Enter`, `Ctrl+X`).
4. Run:
   ```bash
   git add README.md
   git commit -m "docs: add professional README"
   git push origin main
