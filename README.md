# End-to-End MLOps Pipeline on AWS for Real-Time Prediction

[![Python](https://img.shields.io/badge/Python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![Docker](https://img.shields.io/badge/Docker-20.10-blue.svg)](https://www.docker.com/)
[![Flask](https://img.shields.io/badge/Flask-2.0-lightgrey.svg)](https://flask.palletsprojects.com/)
[![CI/CD](https://img.shields.io/badge/CI/CD-GitHub_Actions-green.svg)](https://github.com/features/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project demonstrates a complete, production-grade MLOps pipeline built and deployed entirely on **Amazon Web Services (AWS)**. The use case is a real-time wine quality prediction service, but the core of the project is the robust, automated, and scalable cloud engineering framework.
The entire CI/CD workflow is automated: a `git push` to the main branch triggers a pipeline that builds, tests, and deploys the new version of the application with zero downtime.

---

## 🎥 Project Demo


<img width="1888" height="621" alt="image (2)" src="https://github.com/user-attachments/assets/2e37120b-cfd6-4c81-9275-2fdfd8c6d761" />


---



## 🚀 Overview

This repository contains a complete, production-grade MLOps pipeline built on **AWS**, demonstrating the full lifecycle of a machine learning model. The use case is a real-time wine quality prediction service, but the core of the project is the robust, automated, and scalable cloud engineering framework.

The entire workflow is automated using **GitHub Actions for CI/CD**: a `git push` to the main branch automatically builds a new Docker image, pushes it to a container registry, and deploys it to a production environment running on an EC2 instance.

This project also integrates **MLflow** for robust experiment tracking, model logging, and ensuring reproducibility.

---

## ✨ About MLflow

**MLflow** is a production-grade, open-source platform for managing the end-to-end machine learning lifecycle. In this project, it is used for:

-   **Experiment Tracking:** Logging parameters, code versions, metrics, and output files for every training run.
-   **Model Management:** Storing, versioning, and managing trained models in a centralized registry.
-   **Reproducibility:** Ensuring that every part of the experiment can be reliably reproduced.


---

## ✨ Key Features & Technical Deep Dive

- **Automated CI/CD:** Implemented a full **CI/CD pipeline using AWS CodePipeline**, which automatically triggers on commits to the GitHub repository.
- **Containerization:** The Flask API and ML model are containerized using **Docker**, creating a portable and reproducible system.
- **Cloud Container Registry:** The Docker image is automatically built by AWS CodeBuild and stored in **Amazon Elastic Container Registry (ECR)**.
- **Scalable Deployment:** The containerized application is deployed on **AWS Elastic Container Service (ECS) with Fargate** (or **AWS App Runner**), providing a serverless, auto-scaling, and resilient production environment.
- **Machine Learning Model:** An Elastic Net regression model trained with Scikit-learn to predict wine quality.
- **REST API:** A production-ready API built with **Flask** exposes the model for real-time inference.

---

## 🛠️ Tech Stack

| Category          | Technologies Used                                        |
| ----------------- | -------------------------------------------------------- |
| **Cloud Platform**| **Amazon Web Services (AWS)**                            |
| **CI/CD** | **GitHub Actions** (with a Self-Hosted Runner on EC2) |
| **Containerization**| **Docker, Amazon ECR**                                   |
| **Deployment** | **Amazon EC2** |
| **MLOps & Tracking**| **MLflow, DagsHub** |
| **ML & Data**     | Python, Scikit-learn, Pandas                             |
| **API & Web**     | Flask, HTML/CSS                                          |

---



## ⚙️ MLOps Pipeline Architecture

This project follows a professional, event-driven MLOps architecture:

1.  **Source (GitHub):** A developer pushes a code change to the `main` branch of the GitHub repository.
2.  **CI/CD Trigger (GitHub Actions):** This push automatically triggers a pre-configured workflow in **GitHub Actions**.
3.  **Self-Hosted Runner (EC2):** The GitHub Actions job is picked up by a self-hosted runner configured on an **AWS EC2 instance**.
4.  **Build & Push (Docker & ECR):** The runner executes the CI/CD steps:
    -   It builds the Docker image from the `Dockerfile`.
    -   It logs into **Amazon Elastic Container Registry (ECR)** using credentials stored in GitHub Secrets.
    -   It pushes the new Docker image to our ECR repository.
5.  **Deploy (EC2):** The final step in the workflow pulls the latest image from ECR onto the same EC2 instance and runs the new container, updating the live application.
