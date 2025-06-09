# Book Review Web App – DevOps Project

A full-stack Book Review Web Application with a robust DevOps pipeline using Docker, Kubernetes, and GitHub Actions for CI/CD.

## 📦 Project Structure

```
book-review-app/
├── backend/           # FastAPI backend
├── frontend/          # React frontend
├── k8s/               # Kubernetes manifests
├── .github/workflows/ # CI/CD pipeline
└── docker-compose.yaml
```

## 🚀 Features

- **Backend:** FastAPI (Python)
- **Frontend:** React (Node.js)
- **Database:** PostgreSQL
- **Containerization:** Docker & Docker Compose for local development
- **Orchestration:** Kubernetes manifests (deployments, services, ingress)
- **CI/CD:** Automated build & deploy with GitHub Actions

## 🐳 Getting Started with Docker Compose

1. **Clone the repo:**
   ```sh
   git clone https://github.com/YOUR-USERNAME/book-review-app.git
   cd book-review-app
   ```

2. **Run locally:**
   ```sh
   docker-compose up --build
   ```
   - Frontend: [http://localhost:3000](http://localhost:3000)
   - Backend: [http://localhost:8000](http://localhost:8000)

3. **Stop containers:**
   ```sh
   docker-compose down
   ```

## ☸️ Deploying with Kubernetes

1. **Ensure you have a running Kubernetes cluster** (e.g., minikube, Docker Desktop, or cloud provider).

2. **Apply manifests:**
   ```sh
   kubectl apply -f k8s/namespace.yaml
   kubectl apply -f k8s/postgres-deployment.yaml
   kubectl apply -f k8s/backend-deployment.yaml
   kubectl apply -f k8s/frontend-deployment.yaml
   kubectl apply -f k8s/ingress.yaml
   ```

3. **Access the app:**
   - Set `/etc/hosts`:  
     `127.0.0.1 bookreview.local`
   - Visit [http://bookreview.local](http://bookreview.local)

## 🔁 CI/CD with GitHub Actions

- **Workflow:** `.github/workflows/ci-cd.yaml`
  - Builds and pushes Docker images to Docker Hub.
  - Applies Kubernetes manifests to your cluster.
- **Secrets required:**
  - `DOCKERHUB_USERNAME`
  - `DOCKERHUB_TOKEN`
  - `KUBECONFIG_DATA` (base64-encoded kubeconfig)

## 📂 Directory Details

- **backend/**: FastAPI app and Dockerfile.
- **frontend/**: React app and Dockerfile.
- **k8s/**: Kubernetes deployments, services, and ingress.
- **.github/workflows/**: GitHub Actions pipeline.
- **docker-compose.yaml**: For local multi-container setup.

## 🛠️ Customization

- Update environment variables (like database credentials) in the respective manifest files.
- Change Docker image names to your Docker Hub username.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

---

> **Need help?** Open an issue or contact the maintainer.