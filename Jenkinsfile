pipeline {
    agent { label 'apple' }

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
                sh 'grep -i "<html" Login_page.html || echo "HTML tag missing"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Archiving HTML files...'
                archiveArtifacts artifacts: 'Login_page.html', fingerprint: true
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

