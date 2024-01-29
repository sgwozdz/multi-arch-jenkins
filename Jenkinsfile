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
    stage("Build docker images") {
      steps {
        def amd64 = docker.build("sample-app:amd64", "--platform linux/amd64")
        def arm64 = docker.build("sample-app:arm64", "--platform linux/arm64")
      }
    }
  }
}