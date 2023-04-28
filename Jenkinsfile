pipeline {
    agent {
        node {
            label 'windows'
        }
    }
    stages {
        stage('Build') {
            steps {
                bat 'echo Building...'
            }
        }
        stage('Test') {
            steps {
                bat 'echo Testing...'
            }
        }
        stage('Deploy') {
            steps {
                bat 'echo Deploying...'
            }
        }
    }
}
