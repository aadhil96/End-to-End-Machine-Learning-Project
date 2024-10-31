# End-to-End MLOps Machine Learning Pipeline using GitHub Actions, Docker, AWS ECS, and AWS EC2

This project demonstrates a comprehensive end-to-end MLOps pipeline for deploying machine learning models at scale. Leveraging GitHub Actions for continuous integration (CI) and continuous deployment (CD), Docker for containerization, and AWS ECS and EC2 for deployment, this setup automates the ML lifecycle from model training to production deployment. The project aims to provide a scalable and repeatable pipeline to bring machine learning models into production efficiently and reliably.

## Key Features
- **Automated CI/CD Pipeline with GitHub Actions**: Automatically triggers and runs tests, builds Docker images, and deploys to AWS, streamlining the model deployment process.
- **Docker for Containerization**: Ensures consistent, portable, and isolated environments for the ML model across different stages of development and deployment.
- **AWS ECS and EC2 for Scalable Deployment**: Deploys the model on AWS ECS for containerized workloads and EC2 for scalable compute, allowing flexibility in managing compute resources and costs.
- **Modular Code Structure**: Organized project files for easy extension and maintenance, separating training, serving, and infrastructure configuration.

## Workflow
1. **Data Preparation and Model Training**: Prepare data and train the model locally or using cloud resources. Commit changes to GitHub.
2. **Continuous Integration**: Upon code changes, GitHub Actions runs tests and builds the Docker image.
3. **Continuous Deployment**: GitHub Actions pushes the Docker image to Amazon Elastic Container Registry (ECR) and deploys it to ECS or EC2 instances.
4. **Model Serving**: Model is served as a REST API, capable of handling requests in real-time.


# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image
    - Save the URI: 970547337635.dkr.ecr.ap-south-1.amazonaws.com/mlproj

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
# 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


# 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app
