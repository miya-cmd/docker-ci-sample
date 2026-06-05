pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/miya-cmd/docker-ci-sample.git',
                        credentialsId: 'github-token'
                    ]]
                ])
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f myapp || exit 0'
                bat 'docker run -d --name myapp -p 8080:80 myapp:latest'
                bat 'docker ps'
            }
        }
    }
}
