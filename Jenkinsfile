pipeline {
    agent any
    environment {
        ASPNETCORE_ENVIRONMENT = 'Production'
    }
    stages {
        stage('Clone repository') {
            steps {
                git url: 'https://github.com/Niraj2003/DotNet.git', branch: 'main'
            }
        }
        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build'
            }
        }
        stage('Run tests') {
            steps {
                sh 'dotnet test'
            }
        }
        stage('Publish') {
            steps {
                sh 'dotnet publish -c Release -o ./publish'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp -r ./publish user@hostname:/var/www/myapp'
            }
        }
    }
}
