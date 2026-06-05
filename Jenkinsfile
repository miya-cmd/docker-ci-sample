pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/miya-cmd/docker-ci-sample.git'
                     
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
    }
}
