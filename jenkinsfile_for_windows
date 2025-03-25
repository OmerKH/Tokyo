pipeline {
    agent any

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
