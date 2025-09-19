# End-to-End MLOps Pipeline for a Real-Time Prediction Service

[![Python](https://img.shields.io/badge/Python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![Docker](https://img.shields.io/badge/Docker-20.10-blue.svg)](https://www.docker.com/)
[![Flask](https://img.shields.io/badge/Flask-2.0-lightgrey.svg)](https://flask.palletsprojects.com/)
[![CI/CD](https://img.shields.io/badge/CI/CD-GitHub_Actions-green.svg)](https://github.com/features/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the source code for a complete, production-grade MLOps pipeline built to serve a real-time wine quality prediction model. The core of this project is not just the machine learning model itself, but the robust engineering framework that automates its deployment, ensuring scalability, reproducibility, and continuous integration.

---

## 🎥 Project Demo


<img width="1888" height="621" alt="image (2)" src="https://github.com/user-attachments/assets/2e37120b-cfd6-4c81-9275-2fdfd8c6d761" />



---

## 🎯 The Business Problem & The Solution

**Problem:** Data science teams often build powerful machine learning models that remain stuck in Jupyter Notebooks. The process of deploying these models into a live, scalable, and reliable application is a significant engineering challenge, often referred to as the "last mile" problem of machine learning.

**Solution:** This project tackles that problem head-on by implementing a full MLOps pipeline. It takes a trained Scikit-learn model and deploys it as a containerized REST API, creating a robust system that can be automated and integrated into other business applications. The Wine Quality Prediction app serves as the tangible use case for this powerful engineering framework.

---

## ✨ Key Features

- **ML Model:** An Elastic Net regression model trained to predict wine quality based on physicochemical properties.
- **Prediction API:** A Flask-based REST API that exposes the model for real-time inference.
- **Containerization:** The entire application (API + model) is packaged into a portable, scalable **Docker** container.
- **CI/CD Ready:** The project is structured for automated workflows, including building, testing, and deploying the container.
- **Simple UI:** A basic HTML/CSS frontend to interact with the prediction service.

---

## 🛠️ Tech Stack

- **Language:** Python
- **ML & Data:** Scikit-learn, Pandas, NumPy
- **API & Web:** Flask, HTML/CSS
- **MLOps & Engineering:** Docker, GitHub Actions (for CI/CD), AWS(for deployment)

---

## 🏗️ MLOps Pipeline Architecture

This project is designed to be deployed using a standard CI/CD workflow:

1.  **Code Commit:** A developer pushes a change to this GitHub repository.
2.  **CI Trigger:** A Continuous Integration tool (like GitHub Actions) is automatically triggered.
3.  **Build & Test:** The CI pipeline builds the Docker image and runs any automated tests.
4.  **Push to Registry:** The validated Docker image is pushed to a container registry (e.g., AWS ECR).
5.  **CD Trigger:** A Continuous Delivery trigger deploys the new image to a cloud service (AWS App Runner), updating the live API with zero downtime.
