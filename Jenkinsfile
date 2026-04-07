pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t angular-cicd-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop angular-docker || true'
                sh 'docker rm angular-docker || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8081:80 --name angular-docker angular-cicd-app'
            }
        }
    }
}