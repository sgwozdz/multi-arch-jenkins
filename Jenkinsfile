pipeline {
    agent any
    
    environment {
        DOTNET_CLI_HOME = tool 'dotnet'
        DOCKER_IMAGE_NAME = "sample-app"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build docker image ') {
            steps {
                docker.build("${DOCKER_IMAGE_NAME}:latest-amd64", "--platform linux/amd64 .")
            }
        }
    }
}
