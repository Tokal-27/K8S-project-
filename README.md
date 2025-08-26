# K8S-project-

This project demonstrates deploying a Kubernetes lab environment on **KinD** with Ingress, a **MySQL database**, and an **Authentication service**.

## 📌 Steps Overview

1. **Cluster Setup**
   - Delete any existing KinD cluster.
   - Recreate a cluster with Ingress support and port mappings.
   - Install the NGINX Ingress controller.

2. **MySQL Deployment**
   - Create a headless service for MySQL.
   - Store sensitive values in Kubernetes Secrets.
   - Deploy MySQL using a StatefulSet with persistent storage.
   - Run an init job to create the `weatherapp` database and user.
   - Verify the database and user are accessible.

3. **Authentication Service**
   - Deploy the `weatherapp-auth` service connected to MySQL.
   - Expose it with a ClusterIP service.
   - Verify pods and services are running.

4. **Testing**
   - Use a temporary Alpine pod with curl.
   - Send a POST request to `/users` endpoint.
   - Confirm that users can be added successfully to the database.

---

## 📂 Project Structure

```plaintext
K8S-Project-/
├── mysql/
│   ├── headless-service.yaml
│   ├── statefulset.yaml
│   ├── init-job.yaml
└── auth/
    ├── deployment.yaml
    └── service.yaml
