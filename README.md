# githubactiondeployec2

This project demonstrates how to deploy a Dockerized application to an EC2 instance automatically using GitHub Actions and SSH.

🚀 Features
CI/CD with GitHub Actions

Docker image build & push to DockerHub

Remote SSH deployment to AWS EC2

Fully automated deployment on main branch push

🛠️ Stack
GitHub Actions

Docker / DockerHub

AWS EC2 (Ubuntu)

SSH Key authentication

📁 Project Structure
bash
Copy
Edit
├── .github/workflows/deploy.yml   # GitHub Actions workflow file
├── Dockerfile                     # Dockerfile to build image
├── app/ or source files           # Your app files
└── README.md
⚙️ Setup Guide
1. 🐳 DockerHub Setup
Push your image to DockerHub:

Create a DockerHub account.

Create a repository like: mydockerhubuser/myapp.

2. 🤖 GitHub Secrets
Add the following secrets in your GitHub repo:

Secret Name	Description
DOCKER_USERNAME	Your DockerHub username
DOCKER_PASSWORD	Your DockerHub password or PAT
EC2_HOST	EC2 public IP (e.g. 54.x.x.x)
EC2_USER	Typically ubuntu or ec2-user
EC2_SSH_KEY	Your private key in base64 format

📝 Convert your private key to base64 using:
base64 -w 0 your-key.pem

EC2 Instance Setup
Install Docker:

bash
Copy
Edit
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo usermod -aG docker ubuntu  # Then reboot
Allow HTTP access (port 80) in EC2 Security Group.


