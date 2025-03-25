pipeline {
    agent {
        docker {
            image 'node:18'  // Ensures Node.js is available
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/OmerKH/Tokyo.git'
            }
        }
        stage('Build') {
            steps {
               sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'ls -la'  // List directory contents for debugging
                sh 'npm test'

            }  
            post {
                failure {
                    echo 'Tests failed! Stopping pipeline.'
                    error('Stopping pipeline due to test failure.')
                }
            }
        }
        stage('Run') {
            steps {
                sh 'npm start'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment command here (Docker, Kubernetes, etc.)
            }
        }
    }
}
