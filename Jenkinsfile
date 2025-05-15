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
                bat 'dir' // Use 'ls' if on Linux/Mac
            }
        }

        stage('Build Simulation') {
            steps {
                echo 'Running a simulated build step...'
                bat 'echo Build step executed!'
            }
        }
    }
}
