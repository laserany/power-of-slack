pipeline {
    agent { docker { image 'node:14-alpine' } }
    stages {
        stage('build') {
            steps {
                sh 'npm --version'
            }
        }
        stage('send notifications to slack') {
            steps {
                slackSend (color: "good", channel: "#jenkins", message: "Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}")
            }
        }
    }
}