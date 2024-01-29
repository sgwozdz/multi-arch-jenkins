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
    stage("Build & push docker image") {
      parallel {
        stage("Build & push amd64 docker image") {
          steps {
            script {
              def amd64Image = docker.build("${DOCKER_IMAGE_NAME}:amd64", "--platform linux/amd64 .")
              amd64Image.push()
            }
          }
        }
        stage("Build & push arm64 docker image") {
          steps {
            script {
              def arm64Image = docker.build("${DOCKER_IMAGE_NAME}:arm64", "--platform linux/arm64 .")
              arm64Image.push()
            }
          }
        }
      }
    }
  }
}