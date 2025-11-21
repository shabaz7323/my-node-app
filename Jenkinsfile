pipeline {
    agent any
    stages {
        stage('Clone') {
            steps { git 'https://github.com/your-username/my-node-app.git' }
        }
        stage('Build Docker Image') {
            steps { script { docker.build("my-node-app:latest") } }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh "kubectl apply -f k8s/deployment.yaml"
                sh "kubectl apply -f k8s/service.yaml"
            }
        }
    }
}