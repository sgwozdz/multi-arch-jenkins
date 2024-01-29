pipeline {
  agent any
  environment { 
    DOCKER_IMAGE_NAME = 'sample-app'
  }
  stages {
    stage("Checkout") {
      steps {
        checkout scm
      }
    }
    parallel {
      stage("Build amd64 docker image") {
        steps {
          docker.build("${DOCKER_IMAGE_NAME}:amd64", "--platform linux/amd64 .")
        }
      }
      stage("Build arm64 docker image") {
        steps {
          docker.build("${DOCKER_IMAGE_NAME}:arm64", "--platform linux/arm64 .")
        }
      }
    }
  }
}