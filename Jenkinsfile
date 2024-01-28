pipeline {
    agent any
    
    environment {
        DOTNET_CLI_HOME = tool 'dotnet'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    sh "dotnet build"
                }
            }
        }

        stage('Publish') {
            steps {
                script {
                    sh "dotnet publish -c Release -o ./publish"
                }
            }
        }
    }
}
