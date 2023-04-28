pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
                doGenerateSubmoduleConfigurations: false, 
                extensions: [], submoduleCfg: [], 
                userRemoteConfigs: [[url: 'https://github.com/Niraj2003/DotNet.git']]])
            }
        }

        stage('Build') {
            steps {
                echo 'Building'
                sh 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing'
                sh 'dotnet test'
            }
        }

        stage('Publish') {
            steps {
                echo 'Publishing'
                sh 'dotnet publish'
            }
        }
    }
}