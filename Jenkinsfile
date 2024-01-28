pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE_NAME = "sample-app"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                def customImage = docker.build("my-image:latest")
            }
        }

        // stage('Build docker image ') {
        //     steps {
        //         script{
        //             docker.build("${DOCKER_IMAGE_NAME}:latest-amd64", "--platform linux/amd64 .")
        //         }
        //     }
        // }
    }
}
