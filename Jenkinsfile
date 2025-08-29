pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'main', url: 'https://github.com/prabhu4112/login-page-.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for HTML project'
                sh 'ls -l'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing HTML files...'
                sh 'grep -i "<html" index.html || echo "HTML tag missing"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML files...'
                // Example: copy to /var/www/html or archive artifacts
                sh 'cp -r * /var/www/html/'  // requires proper permissions
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed.'
        }
        success {
            echo 'Pipeline completed successfully.'
        }
    }
}

