# Node.js-hello-world

This repository contains a Node.js "Hello World" application with deployment configurations for Docker and Kubernetes using Jenkins.

``` mermaid
graph LR
A[Git Repository (#93D7AF)] --> B{Checkout Code (#EAF882)}
B --> C{Build Docker Image (#F2E9A7)}
C --> D{Push Docker Image (#FCE4EC)}
D --> E{Deploy to Kubernetes (#D4ECDC)}
E --> F{Application Running ("Hello World!") (#A5D6A7)}
D --> G{Post-Deployment Verification (Optional) (#FCE4EC)}
G --> E
B --> H{Credentials (Git) (#CCD1D9)} [dashed]
D --> I{Credentials (Docker Hub) (#CCD1D9)} [dashed]
E --> J{Credentials (Kubernetes) (#CCD1D9)} [dashed]

style A, B, C, D, E, F, G
    fill:#fff;
    stroke:#333;
    stroke-width: 2px;
    padding: 10px;
    font-size: 14px;
    font-family: sans-serif;
style H, I, J
    fill:#fff;
    stroke:#333;
    stroke-width: 1px;
    padding: 5px;
    font-size: 12px;
    font-family: sans-serif;

'''


