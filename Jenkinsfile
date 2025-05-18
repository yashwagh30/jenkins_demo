pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'yashwagh30/myapp:day59'
    }

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
                bat "docker build -t ${DOCKER_IMAGE} ."
            }
        }

        stage('Login to Docker Hub') {
            steps {
                echo 'Logging into Docker Hub...'
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    bat "docker login -u %USERNAME% -p %PASSWORD%"
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                echo 'Pushing image to Docker Hub...'
                bat "docker push ${DOCKER_IMAGE}"
            }
        }

        stage('Verify Docker Image Locally') {
            steps {
                echo 'Listing local Docker images...'
                bat "docker images"
            }
        }
    }
}
