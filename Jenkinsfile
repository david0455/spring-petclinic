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
            steps {
                bat 'mvn deploy' 
            }
        }
        
    }
}
