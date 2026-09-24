pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t docker-cicd-demo .'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing Docker image...'
                sh 'docker images docker-cicd-demo'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'docker rm -f docker-cicd-demo-container || true'
                sh 'docker run -d --name docker-cicd-demo-container -p 8081:80 docker-cicd-demo'
            }
        }
    }
}
