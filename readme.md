Dockerized Flask App with Jenkins Pipeline

Overview
This project demonstrates a CI workflow using Docker and Jenkins. A Flask application is containerized and deployed automatically using a Jenkins pipeline.

Tech Stack
Python (Flask)
Docker
Jenkins

Project Structure
app.py
Dockerfile
requirements.txt
Jenkinsfile
README.md

Steps to Run

Build Docker Image
docker build -t flask-app .

Run Container
docker run -p 5000:5000 flask-app

Access
http://localhost:5000

Pipeline Flow
1. Jenkins pulls code from GitHub
2. Builds Docker image
3. Stops old container
4. Runs new container
