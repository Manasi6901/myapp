# MyApp - DevOps Pipeline Project

This project demonstrates a complete DevOps pipeline setup using:

- **Docker**: Containerizing the application
- **Jenkins**: CI/CD automation
- **Ansible**: Application deployment
- **Git & GitHub**: Source control
- **Private Docker Registry**: Hosting custom Docker images
- **Kubernetes** (optional): For orchestration

## 🔧 Technologies Used

- Java/Python (backend app)
- Docker
- Jenkins
- Ansible
- Git
- EC2 Instances (AWS)
- Private Docker Registry

## 🚀 Pipeline Workflow

1. Code is pushed to GitHub
2. Jenkins builds Docker image and pushes to private registry
3. Ansible pulls image and runs the container on target server
4. Application is accessible via public IP on port 8080

## 🐳 Docker Commands

```bash
docker build -t myapp .
docker tag myapp:latest <registry-ip>:5000/myapp:latest
docker push <registry-ip>:5000/myapp:latest
ansible-playbook -i hosts deploy.yml


You should see:

Hello from DevOps Pipeline!
