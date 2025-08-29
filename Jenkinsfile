pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/prabhu4112/login-page-.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building the login page..."'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }
    }
}
