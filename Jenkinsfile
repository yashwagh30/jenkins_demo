pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('List Files') {
            steps {
                echo 'Listing files in workspace...'
                bat 'dir' // Use 'ls' for Linux
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing Python dependencies...'
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                echo 'Running tests with pytest...'
                bat 'pytest test_app.py'
            }
        }
    }
}

