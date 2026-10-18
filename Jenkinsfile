pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build') {
            steps {
                echo 'Building HTML project...'
                bat 'if not exist index.html exit /b 1'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing HTML project...'
                bat 'findstr /C:"Welcome to Jenkins" index.html'
            }
        }
    }
    post {
        success { echo 'Pipeline completed successfully!' }
        failure { echo 'Pipeline failed!' }
    }
}
