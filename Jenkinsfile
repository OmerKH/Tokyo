pipeline {
    agent any

    stages {
        stage('Create a Text File') {
            steps {
                bat 'echo. > "emptyfile.txt"'
            }
        }
        stage('Print messege') {
            steps {
                bat  'echo "Hello from Pipeline!"'
            }
        }
    }   
}
