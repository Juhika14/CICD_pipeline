# InteliPaaT DevOps Certification Project

This project is part of the Intel iPaaT DevOps Certification Training. It demonstrates a complete CI/CD pipeline using **Jenkins**, **Docker**, **GitHub**, and **Ansible**.

---

## Project Overview

The pipeline is designed to:

1. Automatically trigger on code changes to the `main` branch in GitHub.
2. Build a Docker image from the codebase.
3. Test the Docker container.
4. Deploy the container to a production environment on success.

---

##  Tech Stack

- **Jenkins** 
- **Docker**
- **Ansible**
- **GitHub**
- **Ubuntu** (Agent Node)

---

## CI/CD Pipeline Structure

### 🔧 1. `Build_Job` (refer to Build_job.txt)
- Triggered automatically by GitHub webhook on `main` branch.
- Clones the GitHub repository.
- Builds a Docker image from the app.
- Triggers `Test_Job` with the built image tag.

### 2. `Test_Job` refer to Test_job.txt
- Runs the Docker image in a container.
- Performs a basic HTTP health check (`curl`).
- If the test passes, triggers the `Prod_Job`.

###  3. `Prod_Job` Refer to the (Prod_job.txt)
- Stops any existing container.
- Runs the new Docker image as a production container on port `80`.

---

## ⚙️ Infrastructure Setup (Ansible)

All necessary installations and configurations for Jenkins, Docker, and required system dependencies were automated using an **Ansible playbook**.

The Ansible script:
- Installs Jenkins and Docker
- Adds Jenkins user to Docker group
- Configures required packages
- Sets up and starts Jenkins service

---

## 📂 Repository Structure

