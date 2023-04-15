# AWS CICD



## 1. Copy files

```
app.py
setup.py
requirements.txt
src
templates
artifacts
```



## 2. Create files

```shell
touch Dockerfile
```

- Check docker build locally



## 3. Create GitHub Action

- Go to GitHub repository and click Actions
- In Deployment, find Delopy to Amazon ECS and click Configure 



## 4. Add AWS IAM user

- Step1 Add user
- Step 2 
  - Permisions options: Attach polices diectly
  - Permissons policies: AmazonEC2ContainerRegistryFullAccess, AmazonEC2FullAccess
- Step 3 Create user



## 5. Setup Access keys

- Select user and go to Access keys
- Create access key: Command Line Interface (CLI)
- Download accessKey.csv



## 6. ECR

- Create repository
- Repository name
- Copy the URL



## 7. EC2

- Launch instance
- Name and tags: studentindicator
- Select Ubuntu
- Key pair: create new key pair
- Network settings: select Allow HTTPS and Allow HTTP
- Launch



## 8. Connect to Instance

- go to studentidicator instance and click connect

```shell
sudo apt-get update -y

sudo apt-get upgrade

curl -fsSL https://get.docker.com -o get-docker.sh

sudo sh get-docker.sh

sudo usermod -aG docker ubuntu

newgrp docker
```



## 9. Setup Actions Runner

- Go to Settings and click Actions and Runner
- Click New self-hosted runner
- Runner image: Linux
- Execute the Download command in EC2 instance
- Execute the Configure command and Enter the name: self-hosted



## 10. Create Secrets 

- Go to Settings and click Secrets and variables
- Select Actions and click New repository secret
- Name: AWS_ACCESS_KEY_ID