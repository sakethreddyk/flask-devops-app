# 🚀 Flask DevOps Pipeline with Docker, GitHub Actions, Prometheus & Grafana

This project demonstrates a complete DevOps workflow including app containerization, CI/CD, and real-time monitoring using Prometheus and Grafana. It is built using a simple Flask web application that exposes metrics at `/metrics`.

## 🧰 Tech Stack
- Backend: Python (Flask)
- Containerization: Docker
- CI/CD: GitHub Actions
- Monitoring: Prometheus, Grafana
- Orchestration: Docker Compose
- Registry: DockerHub

## 📁 Project Structure
- `app.py` – Flask app exposing metrics
- `Dockerfile` – Builds a container image
- `requirements.txt` – Python dependencies
- `.github/workflows/docker-ci.yml` – CI/CD pipeline
- `docker-compose.yml` – Runs all services
- `prometheus.yml` – Prometheus config

## 🔨 Step-by-Step Setup

### 1️⃣ Build Flask App
Created a Python Flask app that returns a simple message and exposes metrics to Prometheus at `/metrics`.

### 2️⃣ Dockerize the App
Wrote a Dockerfile to containerize the app and tested it with `docker build` and `docker run`.

### 3️⃣ Push Code to GitHub
Initialized a Git repo, added remote, committed code, and pushed to `main` branch on GitHub.

### 4️⃣ Set Up GitHub Actions for CI/CD
- Created secrets: `DOCKER_USERNAME`, `DOCKER_PASSWORD`
- Added GitHub Actions workflow to build and push Docker image to DockerHub automatically on every push to `main`.

### 5️⃣ Docker Compose Setup
Used Docker Compose to run:
- Flask app
- Prometheus (scraping `/metrics`)
- Grafana (visualizing metrics)

### 6️⃣ Prometheus Configuration
Set Prometheus to scrape metrics from the Flask container every 15 seconds using a `prometheus.yml` file.

### 7️⃣ Grafana Setup
- Accessed Grafana at `localhost:3000`
- Logged in with default creds (`admin`/`admin`)
- Added Prometheus as a data source
- Created a dashboard visualizing `http_requests_total`

### 8️⃣ Test End-to-End Flow
- Made a change in `app.py` and pushed to GitHub
- GitHub Actions rebuilt the image and pushed to DockerHub
- Pulled the new image and restarted Docker Compose
- Confirmed updated response and updated metrics

## 💡 How It Works
| Action                     | Result                                      |
|----------------------------|---------------------------------------------|
| Code push to GitHub        | GitHub Actions runs CI/CD pipeline          |
| Image build and push       | DockerHub stores new image version          |
| Compose restart            | Runs updated image locally with monitoring  |
| Prometheus scrapes metrics | Grafana visualizes live traffic             |

## ✅ Future Enhancements
- Add unit tests to pipeline
- Add Slack or email alerting
- Deploy to AWS EC2 or Azure VM
- Use Kubernetes + Helm

## 🙌 Author
**Saketh Reddy K**  
DevOps Engineer | Cloud Enthusiast  
GitHub: https://github.com/sakethreddyk
