pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/riyapathania08/k8s-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t riyapathania08/my-app .'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push riyapathania08/my-app'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}