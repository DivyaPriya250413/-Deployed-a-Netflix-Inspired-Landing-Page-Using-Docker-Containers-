# 🎬 Netflix-Inspired Landing Page | Docker | AWS EC2

![Uploading Netflix Landing Page Docker Architecture.png…]()

## 📌 Project Overview

This project demonstrates deploying a Netflix-inspired responsive landing page using Docker containers on an Ubuntu EC2 instance hosted on AWS.

The objective of this project is to gain hands-on experience with Linux, Docker, containerization, and cloud deployment.

## 🛠️ Technologies Used

- AWS EC2
- Ubuntu Linux
- Docker
- HTML
- CSS
- JavaScript

## 🏗️ Architecture

User Browser → AWS EC2 → Ubuntu → Docker Engine → Docker Container → Nginx → Netflix Landing Page

## 🚀 Deployment Steps

### Step 1: Launch AWS EC2 Instance

1. Log in to AWS Management Console.
2. Navigate to EC2.
3. Launch an Ubuntu instance.
4. Select an instance type.
5. Create or select a key pair.
6. Configure Security Group inbound rules:

| Type | Port | Source |
|---|---|---|
| SSH | 22 | My IP |
| HTTP | 80 | Anywhere (0.0.0.0/0) |

### Step 2: Connect to EC2

Connect to your instance using SSH:

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### Step 3: Update Ubuntu packages

```bash
sudo apt update -y
sudo apt upgrade -y
```

### Step 4: Install Docker

```bash
sudo apt install docker.io -y
```

Start and enable Docker:

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Verify Docker:

```bash
docker --version
```

### Step 5: Create project directory

```bash
mkdir netflix-landing-page
cd netflix-landing-page
```

### Step 6: Create HTML file

Create the website file:

```bash
nano index.html
```

Add your Netflix-inspired landing page HTML, CSS and JavaScript code to this file.

Save the file.

### Step 7: Create Dockerfile

```bash
nano Dockerfile
```

Add the following:

```dockerfile
FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

### Step 8: Build Docker Image

```bash
sudo docker build -t netflix-landing-page .
```

Verify the image:

```bash
sudo docker images
```

### Step 9: Run Docker Container

```bash
sudo docker run -d -p 80:80 --name netflix-app netflix-landing-page
```

### Step 10: Verify Container

```bash
sudo docker ps
```

### Step 11: Access the Website

Open your browser and enter:

```text
http://YOUR-EC2-PUBLIC-IP
```

Your Netflix-inspired landing page should now be accessible.

## 📸 Project Features

- Netflix-inspired UI
- Responsive design
- Movie and TV show sections
- Hover animations
- Docker container deployment
- AWS EC2 hosting

## 📚 Learning Outcomes

- Linux package management using APT
- Docker installation and configuration
- Docker image building
- Docker container management
- Web application deployment on AWS EC2
- Understanding containerization concepts

## 🔮 Future Improvements

- Push Docker image to Docker Hub
- Configure CI/CD using GitHub Actions
- Deploy using Docker Compose
- Configure a custom domain
- Add HTTPS using SSL/TLS

## 👨‍💻 Author

Aspiring DevOps Engineer | Learning Linux, Docker, AWS and Cloud Technologies

---

⭐ If you find this project useful, feel free to explore and contribute!
