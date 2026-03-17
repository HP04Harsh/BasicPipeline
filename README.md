# 🌐 Gondia Directory: Automated CI/CD Pipeline

This project demonstrates a streamlined **DevOps pipeline** for a static web application. It automates the entire process of building, containerizing, and testing a directory site for **Gondia, Maharashtra** using **Docker**, **NGINX**, and **GitHub Actions**.

The main goal is to showcase an "Infrastructure as Code" approach where every code change is automatically verified through a pipeline before deployment.

---

## 🏗 System Architecture & Workflow

The following diagram illustrates the fully automated pipeline workflow that is executed every time code is pushed to the `main` branch. It visualizes the logic in your [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) file.



### Detailed Workflow Description

1.  **Trigger:** A developer pushes changes to the `main` branch.
2.  **Pipeline Activation:** GitHub Actions detects the push and starts the defined workflow (`deploy.yml`).
3.  **Docker Build:** The pipeline uses the `Dockerfile` to create a new, updated Docker image containing your `index.html`.
4.  **Health Check:** It then spins up the new NGINX container.
5.  **Automated Verification:** The workflow executes a `curl` test (`curl localhost:8080`) to confirm the web server is successfully responding with a `200 OK` status.
6.  **Status Report:** If the test passes, the pipeline completes successfully. If it fails, you are notified of the error.

---

## 🚀 Tech Stack

| Technology | Purpose |
| :--- | :--- |
| **HTML5 / CSS3** | Frontend content for the Gondia Directory website. |
| **Docker** | Containerization of the application and its environment. |
| **NGINX** | High-performance web server that serves the static files. |
| **GitHub Actions** | Automated CI/CD platform that executes the pipeline. |

<img width="1024" height="659" alt="image" src="https://github.com/user-attachments/assets/da1416fc-48b1-41cb-8a98-2aab08b6a584" />

---

## 📂 Project Structure

```text
.
├── .github/workflows/
│   └── deploy.yml      # The CI/CD "brain" (Workflow Automation)
├── index.html          # Main website file
├── Dockerfile          # Instructions to create the NGINX image
└── README.md           # Documentation (You are reading this)

