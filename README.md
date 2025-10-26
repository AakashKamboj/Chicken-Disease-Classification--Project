🐔 Chicken-Disease-Classification--Project

🧠 My Contributions
🚀 This repository is a customized and enhanced version of EntBappy’s Chicken Disease Classification Project.
I debugged TensorFlow issues, upgraded the environment, and implemented CI/CD for AWS deployment.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9-blue?logo=python" />
  <img src="https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow" />
  <img src="https://img.shields.io/badge/Docker-Enabled-blue?logo=docker" />
  <img src="https://img.shields.io/badge/AWS-t2.large-success?logo=amazonaws" />
  <img src="https://img.shields.io/badge/CI/CD-GitHub%20Actions-black?logo=githubactions" />
</p>

�
�
￼ ￼ ￼ ￼ ￼ 

🚀 Technical Enhancements
Environment Upgrade: Migrated from Python 3.8 → Python 3.9, ensuring modern dependency support and compatibility.
Docker Modernization: Updated base image from python:3.8-slim-buster → python:3.9-bookworm, improving build security and reducing vulnerabilities.

TensorFlow Fixes:
Fixed eager execution error:

import tensorflow as tf
tf.compat.v1.enable_eager_execution()
tf.config.run_functions_eagerly(True)

Fixed optimizer mismatch warning by recompiling with fresh Adam optimizer:

from tensorflow.keras.optimizers import Adam
self.model.compile(
    optimizer=Adam(learning_rate=0.001),
    loss="categorical_crossentropy",
    metrics=["accuracy"]
)

- Training Pipeline Debugging: Ensured correct function sequence and callbacks (get_base_model(), train_valid_generator(), train()), improving model reproducibility.

⚙ CI/CD & DevOps Improvements

- Implemented GitHub Actions CI/CD pipeline for automated Docker build and deployment.
- Configured OIDC authentication and self-hosted runner for secure deployments on AWS EC2.
- Successfully deployed containerized app on AWS EC2 t2.large instance (tested under a free-tier account).
- Optimized workflow for low-cost deployment by managing instance size, resources, and container lifecycle.

🧩 Impact

- Resolved all major TensorFlow runtime and optimizer issues.
- Achieved end-to-end MLOps automation (training → container → deployment).
- Demonstrated capability to debug and scale an open-source project with AWS DevOps practices.

🐔 Chicken Disease Classification Project
(Original project by EntBappy – retained for reference)
🎯 Goal: Identify chicken diseases using image-based deep learning.
📦 Base Author: EntBappy


## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml


# How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Aakashkamboj/Chicken-Disease-Classification--Project
```
### STEP 01- Create a conda environment after opening the repository

```bash
conda create -n cnncls python=3.9 -y
```

```bash
conda activate cnncls
```


### STEP 02- install the requirements
```bash
pip install -r requirements.txt
```


```bash
# Finally run the following command
python app.py
```

Now,
```bash
open up you local host and port
```


### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag



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
    - Save the URI: 566373416292.dkr.ecr.us-east-1.amazonaws.com/chicken

	
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




# AZURE-CICD-Deployment-with-Github-Actions

## Save pass:

<!-- s3cEZKH5yytiVnJ3h+eI3qhhzf9q1vNwEi6+q+WGdd+ACRCZ7JD6 -->


## Run from terminal:

docker build -t chickenapp.azurecr.io/chicken:latest .

docker login chickenapp.azurecr.io

docker push chickenapp.azurecr.io/chicken:latest


## Deployment Steps :

1. Build the Docker image of the Source Code
2. Push the Docker image to Container Registry
3. Launch the Web App Server in Azure 
4. Pull the Docker image from the container registry to Web App server and run 

🧬 Project Overview
This project is an end-to-end deep learning pipeline for classifying chicken diseases using CNN and Transfer Learning.
Main Components:
Data versioning with DVC
Model training using TensorFlow/Keras
Containerization with Docker
CI/CD using GitHub Actions
Cloud deployment on AWS EC2

🧰 Tech Stack

Category
Tools/Tech
Language
Python 3.9
Frameworks
TensorFlow, Keras
Versioning
Git, DVC
Containerization
Docker
Deployment
AWS EC2
Automation
GitHub Actions
IDE/Terminal
VS Code, Git Bash

⚡ Installation
Bash
conda create -n cnncls python=3.9 -y
conda activate cnncls
pip install -r requirements.txt

🐳 Docker Setup
Bash
docker build -t chicken-classifier:latest .
docker run -p 8080:8080 chicken-classifier:latest

🚀 Deployment
This project supports automated CI/CD through GitHub Actions and can be deployed on AWS EC2 using Docker.
👨‍💻 Author
Aakash Kamboj

💡⭐ Support
If you find this repository helpful, give it a ⭐ on GitHub!
“Debugging teaches you more than tutorials ever will.” 