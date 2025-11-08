# Node.js Docker App with GitHub Actions CI/CD

A demonstration of containerized Node.js application deployment using Docker and automated CI/CD pipeline with GitHub Actions for Minikube.

> **Note**: This repository showcases CI/CD pipeline implementation. The base Node.js application serves as a sample for demonstrating DevOps automation practices.

## 🚀 Features

- **CI/CD Pipeline Implementation** - Complete GitHub Actions workflow for automated deployment
- **Docker containerization** - Production-ready containerization setup  
- **Kubernetes deployment** - Complete K8s manifests and deployment strategy
- **Minikube integration** - Local Kubernetes testing and deployment automation
- **DevOps Best Practices** - Demonstrates modern deployment workflows

## 📋 Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Node.js](https://nodejs.org/) (v14 or higher)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/) (for local K8s testing)

## 🛠️ Quick Start

### Local Development

```bash
# Clone the repository
git clone https://github.com/JuanEstebanOsma1012/gh_actions_test
cd gh_actions

# Install dependencies
npm install

# Run the application
npm start
```

The application will be available at `http://localhost:3000`

### Docker Build & Run

```bash
# Build Docker image
docker build -t nodejs-app:latest .

# Run container
docker run -p 3000:3000 nodejs-app:latest
```

### Kubernetes Deployment

```bash
# Start Minikube
minikube start

# Deploy to Kubernetes
kubectl apply -f k8s-node-app.yaml

# Check deployment
kubectl get pods
kubectl get services

# Access the service
minikube service nodejs-app --url
```

## 🔄 CI/CD Pipeline

The GitHub Actions workflow (`.github/workflows/deploy-to-minikube-github-actions.yaml`) automatically:

1. **Builds** the Docker image
2. **Sets up** Minikube environment
3. **Deploys** the application to Kubernetes
4. **Verifies** the deployment
5. **Exposes** service URLs for testing

### Workflow Triggers

- Runs on every `push` to any branch
- Uses Ubuntu latest runner environment

## 📁 Project Structure

```
.
├── .github/workflows/
│   └── deploy-to-minikube-github-actions.yaml  # CI/CD pipeline
├── Dockerfile                                   # Container definition
├── k8s-node-app.yaml                          # Kubernetes manifests
├── package.json                                # Node.js dependencies
├── server.js                                   # Main application
└── README.md                                   # This file
```

## 🔧 Configuration

### Application Settings

- **Port**: 3000 (configurable in `server.js`)
- **Host**: 0.0.0.0 (all interfaces)

### Kubernetes Resources

- **Deployment**: 1 replica of the Node.js app
- **Service**: NodePort type exposing port 80→3000

## 🚦 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/`      | GET    | Returns "Hello World" |

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

The CI/CD pipeline and DevOps configuration files are licensed under the [MIT License](LICENSE).

**Note**: This license applies specifically to the CI/CD pipeline and DevOps automation created by Juan Esteban Osma. The base Node.js application may have different licensing terms.

## 📧 Contact

Juan Castanio - juan.castanio@example.com

Project Link: [https://github.com/JuanEstebanOsma1012/gh_actions_test](https://github.com/JuanEstebanOsma1012/gh_actions_test)

---

**⭐ Star this repo if you found it helpful!**
