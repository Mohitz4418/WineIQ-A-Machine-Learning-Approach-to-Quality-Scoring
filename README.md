# WineIQ-A-Machine-Learning-Approach-to-Quality-Scoring
Wine Quality Prediction is a machine learning project designed to predict the quality of wine based on physicochemical features such as acidity, sugar, pH, and alcohol content. The project implements an end-to-end pipeline—from model training to containerized deployment—using modern MLOps practices.

## Key features of this project include:

🔍 ML Model: Trained using a classification algorithm on the Wine Quality dataset to predict quality scores.

🐳 Dockerized Application: The model is wrapped in a lightweight Docker container for portability and reproducibility.

🔁 CI/CD with GitHub Actions: Automates the build and push process of the Docker image to Amazon ECR (Elastic Container Registry) whenever changes are pushed to the GitHub repository.

☁️ AWS EC2 Deployment: The Docker image is pulled and deployed on an EC2 instance for serving predictions via a REST API.

🔐 IAM Roles & Security: AWS IAM roles and policies are used to securely authorize ECR access and deploy infrastructure with best practices.

This project showcases how to bridge machine learning with DevOps tools to deploy scalable, production-ready applications on the cloud.

## Workflow for this project.

1. Update config.yaml
2. Update schema.yaml
3. Update params.yaml
4. Update the entity 
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline
8. Update the main.py
9. Update the app.py

## How to run?

### STEPS:

```bash
conda create -n wine_project python=3.8 -y 
```

```bash
conda activate wine_project
```

```bash
pip install -r requirements.txt
```

```bash
python app.py
```

```bash
Now open up your local host 0.0.0.0:8080
```

## AWS-CICD-Deployment-with-Github-Actions

### 1. Login to AWS console.

### 2. Create IAM user for deployment

	With specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	Description: About the deployment

	1. Build docker image of the source code (In windows : type nul > Dockerfile, Linux : touch Dockerfile)

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
### 3. Create ECR Repo to Store/Save Docker Image
    - Save the URI: 136566696263.dkr.ecr.us-east-1.amazonaws.com/mlproject

	
### 4. Create EC2 Machine (Ubuntu) 

### 5. Open EC2 and Install Docker in EC2 Machine:

    # Optional

	sudo apt-get update -y

	sudo apt-get upgrade
	
	# Required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
### 6. Configure EC2 as self-hosted runner:
    setting > actions > runner > new self hosted runner > choose os > then run command one by one


### 7. Setup github secrets:

    AWS_ACCESS_KEY_ID =

    AWS_SECRET_ACCESS_KEY =

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo >> 566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app

