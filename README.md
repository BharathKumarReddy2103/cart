# Roboshop Cart Microservice CICD

Welcome to the **Roboshop Cart Microservice** repository.

This service is a core component of the **Roboshop Application**, a microservices-based e-commerce platform for selling robots.

---

## Overview

The **Cart microservice** manages the shopping cart functionality within the Roboshop ecosystem, allowing users to add, update, and remove items in their shopping cart. This repository encapsulates all source code, infrastructure automation, and CI/CD pipelines required for the Cart service.

---

## Key Features

- **Microservices Architecture:**  
  Built for scalability, resilience, and independent deployment.

- **Cloud-Native Deployment:**  
  Deployed on AWS EKS (Elastic Kubernetes Service) for high availability and robust orchestration.

- **CI/CD Powered by Jenkins:**  
  Automated build, test, and deployment pipelines using Jenkins, leveraging a [shared Jenkins library](https://github.com/BharathKumarReddy2103/jenkins-shared-library) for consistency and maintainability.

- **Containerized with Docker:**  
  Includes a Dockerfile for building lightweight, production-ready containers.

---

## Repository Structure

- `src/` - Cart service source code
- `Dockerfile` - Container build instructions
- `Jenkinsfile` - CI/CD pipeline definition
- `charts/` or `k8s/` - Kubernetes manifests (if present)
- `README.md` - Documentation

---

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/)
- [Jenkins](https://www.jenkins.io/) with access to the [shared library](https://github.com/BharathKumarReddy2103/jenkins-shared-library)
- [AWS CLI](https://aws.amazon.com/cli/) and [kubectl](https://kubernetes.io/docs/tasks/tools/)
- Access to an AWS EKS Cluster

### Clone the Repository

```bash
git clone https://github.com/BharathKumarReddy2103/cart.git
cd cart
```

### Build Docker Image

```bash
docker build -t roboshop-cart:latest .
```

### Running Locally

```bash
docker run -p 8080:8080 roboshop-cart:latest
```

### Deploying to EKS

1. Update Kubernetes manifests (if present) with the correct image and configurations.
2. Apply to your EKS cluster:

    ```bash
    kubectl apply -f k8s/
    ```

---

## CI/CD Pipeline

This repository uses a **Jenkinsfile** for pipeline automation. Key steps include:

- Checkout & build
- Unit testing
- Docker image build & push
- Deployment to AWS EKS

The pipeline utilizes a custom [Jenkins shared library](https://github.com/BharathKumarReddy2103/jenkins-shared-library) for reusable CI/CD logic.

---

## Contributing

Contributions are welcome. Please open issues or submit pull requests for improvements and bug fixes.

---

## License

This project is licensed under the MIT License.

## Contact

For questions or support, please create an issue or contact [BharathKumarReddy2103](https://github.com/BharathKumarReddy2103).
