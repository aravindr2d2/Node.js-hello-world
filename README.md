# Node.js-hello-world

This repository contains a Node.js "Hello World" application with deployment configurations for Docker and Kubernetes using Jenkins.



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


graph TD
    styleDef action fill:#f9f9f9,stroke:#333,stroke-width:2px
    styleDef creds fill:#e6e6e6,stroke:#333,stroke-width:2px,dashed
    styleDef optional fill:#f0e68c,stroke:#333,stroke-width:2px

    A(Git Repository) -->|Checkout| B(Checkout Code)
    B -->|Build| C(Build Docker Image)
    C -->|Push| D(Push Docker Image)
    D -->|Deploy| E(Deploy to Kubernetes)
    E -->|Running| F(Application Running\n"Hello World!")
    D -->|Verify| G(Post-Deployment Verification [Optional])
    G --> E
    
    B -. "Git Credentials" .-> H{{Credentials (Git)}}
    D -. "Docker Hub Credentials" .-> I{{Credentials (Docker Hub)}}
    E -. "Kubernetes Credentials" .-> J{{Credentials (Kubernetes)}}

    class B,C,D,E action
    class H,I,J creds
    class G optional
