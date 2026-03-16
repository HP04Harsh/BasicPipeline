# 🌐 Gondia Static Website Deployment with GitHub Actions

This project demonstrates a **simple DevOps CI/CD pipeline** that deploys a static website using **Docker and NGINX** through **GitHub Actions**.

The website contains basic information about **Gondia, Maharashtra**, and is automatically built and deployed inside a container whenever code is pushed to the repository.

---

## 🚀 Tech Stack

* **HTML / CSS** – Static website
* **Docker** – Containerization
* **NGINX** – Web server to serve the static site
* **GitHub Actions** – CI/CD pipeline

---

## 📁 Project Structure

```
.
├── index.html
├── Dockerfile
└── .github
    └── workflows
        └── deploy.yml
```

---

## ⚙️ How the Pipeline Works

1. Developer pushes code to the `main` branch.
2. GitHub Actions workflow is triggered.
3. The repository is checked out.
4. A Docker image is built using the `Dockerfile`.
5. A container is started using NGINX.
6. The static website is served from the container.
7. A `curl` command verifies the website is accessible.

Pipeline Flow:

```
GitHub Push
     ↓
GitHub Actions
     ↓
Docker Build
     ↓
NGINX Container
     ↓
Static Website Served
```

---

## 🐳 Docker Configuration

The Dockerfile uses the official NGINX image and copies the static site into the web root.

```
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

---

## 🔄 GitHub Actions Workflow

The pipeline builds and runs the container automatically.

Workflow location:

```
.github/workflows/deploy.yml
```

Main steps include:

* Checkout repository
* Build Docker image
* Run NGINX container
* Test site availability

---

## 💻 Run Locally

You can test the application locally using Docker.

### Build Image

```
docker build -t gondia-static-site .
```

### Run Container

```
docker run -p 8080:80 gondia-static-site
```

### Open in Browser

```
http://localhost:8080
```

---

## 📌 Notes

* The GitHub Actions runner runs inside a temporary virtual machine.
* The website is tested inside the runner using `curl`.
* To make the site publicly accessible, you would deploy it to a server or cloud platform.

---

## 🎯 Purpose of This Project

This project is created for learning and demonstrating:

* Basic CI/CD pipelines
* Docker containerization
* Static site deployment using NGINX
* GitHub Actions automation

---

## 👨‍💻 Author

Harsh Pardhi

---

⭐ If you found this useful, feel free to star the repository!
