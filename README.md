# Node.js-hello-world

This repository contains a Node.js "Hello World" application with deployment configurations for Docker and Kubernetes using Jenkins.



graph TD
    A[Git Repository] --> B{Checkout Code}
    B -->|1. Build Image| C{Build Docker Image}
    C -->|2. Push Image| D{Push Docker Image}
    D -->|3. Deploy| E{Deploy to Kubernetes}
    E -->|4. Application Running| F[Application Running ("Hello World!")]
    D -->|Optional| G{Post-Deployment Verification}
    G --> E
    B -->|Credentials| H[Credentials (Git)]
    D -.->|Credentials| I[Credentials (Docker Hub)]
    E -.->|Credentials| J[Credentials (Kubernetes)]

    classDef default fill:#f9f,stroke:#333,stroke-width:4px;
    classDef optional fill:#bbf,stroke:#f66,stroke-dasharray: 5,5;
    class A,B,C,D,E,F default;
    class G optional;
    class H,I,J default;

    linkStyle default stroke:#f66,stroke-width:2px,fill:none;
