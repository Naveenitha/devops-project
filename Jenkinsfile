pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t naveenitha/devops-project:v1 .'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker push naveenitha/devops-project:v1'
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
