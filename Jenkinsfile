pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean' 
            }
        }
        stage('Testing') {
            steps {
                bat 'mvn test' 
            }
        }
        stage('Package') {
            steps {
                bat 'mvn package' 
            }
        }
        stage('Deploy') {
            when {
                branch "master"
            }
            steps {
                bat 'mvn deploy' 
            }
        }        
    }
    post{
        success{
            slackSend color: "good", message: "Success: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
        }
        failure{
            slackSend color: "warning", message: "Failure: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
        }
        
    }
}
