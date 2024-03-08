# Node.js-hello-world

This repository contains a Node.js "Hello World" application with deployment configurations for Docker and Kubernetes using Jenkins.


```mermaid
graph LR
A[Git Repository] --> B{Checkout Code}
B --> C{Build Docker Image}
C --> D{Push Docker Image}
D --> E{Deploy to Kubernetes}
E --> F{Application Running ("Hello World!")}
D --> G{Post-Deployment Verification (Optional)}
G --> E
B --> H{Credentials (Git)}
D --> I{Credentials (Docker Hub)}
E --> J{Credentials (Kubernetes)}
```


