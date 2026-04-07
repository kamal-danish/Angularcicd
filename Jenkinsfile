pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t angular-cicd-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker stop angular-docker || exit 0'
                bat 'docker rm angular-docker || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name angular-docker angular-cicd-app'
            }
        }
    }
}