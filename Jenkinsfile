pipeline {
    agent any

    stages {
        stage('Checkout code') {
            steps {
                git branch: 'master', credentialsId: 'your-git-credentials-id' (if using Git)
            }
        }
        stage('Build Docker image') {
            steps {
                sh 'docker build -t hello-world .'
            }
        }
        stage('Push Docker image') {
            steps {
                // Login to your Docker registry (if pushing to a private registry)
                withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "docker login -u ${USERNAME} -p ${PASSWORD}"
                }
                sh 'docker push hello-world'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                // Define deployment manifest (deployment.yaml)
                script {
                    def deployment = """
apiVersion: apps/v1
kind: Deployment
metadata:
  name: hello-world-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: hello-world
  template:
    metadata:
      labels:
        app: hello-world
    spec:
      containers:
      - name: hello-world
        image: hello-world:latest
        port:
        - containerPort: 3000
"""
                    writeFile label: 'deployment.yaml', content: deployment
                }
                // Apply the deployment manifest using kubectl
                kubernetesApply file: 'deployment.yaml'
            }
        }
    }
}
