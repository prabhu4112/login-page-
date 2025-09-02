pipeline {
    agent any
    environment {
        APP_NAME = "MyApp"
    }
    stages {
        stage('Set Build Name & Description') {
            steps {
                script {
                    currentBuild.displayName = "#${env.BUILD_NUMBER} - ${APP_NAME}"
                    currentBuild.description = "Triggered by Jenkins Pipeline"
                }
            }
        }
        stage('Trigger Another Job') {
            steps {
                build job: 'SecondJob', parameters: [
                    string(name: 'BRANCH', value: 'main')
                ]
            }
        }
        stage('Notify Slack') {
            steps {
                slackSend(channel: '#devops-alerts', 
                          message: "Build ${env.JOB_NAME} #${env.BUILD_NUMBER} completed successfully!")
            }
        }
    }
}
