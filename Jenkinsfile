pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo 'Cloning code...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t myapp:day58 .'
            }
        }

        stage('Verify Docker Image') {
            steps {
                echo 'Listing Docker images...'
                bat 'docker images'
            }
        }
    }
}
