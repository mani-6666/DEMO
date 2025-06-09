# 🚀 Final Task: CI/CD Pipeline with GitHub Actions & Docker (Local Deployment)

This project demonstrates how to build a complete CI/CD pipeline using GitHub Actions, Docker, and Docker Hub — and deploy the application locally without using cloud services.

---

## 🎯 Objective

- Automate testing, Docker image build, and push to Docker Hub using GitHub Actions.
- Deploy and test the Docker image locally using Docker or Minikube.

---

## 🛠 Tools & Technologies Used

- GitHub Actions
- Docker & Docker Hub
- Node.js (Express)
- Dockerfile & docker-compose
- WSL on Windows (Ubuntu)
- Minikube (optional)
- YAML

---

## 📁 Project Structure

```
ci-cd-local/
├── Dockerfile
├── docker-compose.yml
├── package.json
├── src/
│   └── index.js
├── .github/
│   └── workflows/
│       └── main.yml
├── screenshots/
│   └── *.png (documented steps)
```

> ✅ `package.json` is correctly placed in the root directory.

---

## ⚙️ Steps to Build the Project

### 1. Created a simple Express Node.js app (`src/index.js`)
### 2. Added a `package.json` in the root with necessary dependencies and scripts
### 3. Wrote a `Dockerfile` to containerize the app
### 4. Created a GitHub Actions workflow (`.github/workflows/main.yml`) to:
   - Checkout repo
   - Log in to Docker Hub
   - Build Docker image
   - Push image to Docker Hub

### 5. Successfully triggered CI/CD pipeline on `push to main`
### 6. Pulled image and ran locally on WSL using:
```bash
docker run -d -p 3000:3000 your-dockerhub-username/ci-cd-app
```

### 7. Accessed app using:
```
http://localhost:3000
```
or WSL IP if needed.

---

## 📸 Screenshots Included

- GitHub Actions logs
- Docker build output
- Local container running
- Web app accessible in browser

---

## ✅ Outcome

Successfully implemented a real-world CI/CD pipeline without cloud services. This project reinforces end-to-end understanding of automation, containerization, and local deployment using DevOps best practices.

---

## 🔗 Docker Hub Image

👉 https://hub.docker.com/r/your-dockerhub-username/ci-cd-app

---

## 📌 Author

Manikanta Nandyala  
DevOps Enthusiast | Hands-on with GitHub Actions | Docker | Jenkins | CI/CD | Node.js
