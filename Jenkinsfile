pipeline {
  agent any
  stages {
    stage('Application Build') {
      steps {
        sh 'sh ./scripts/build.sh'
      }
    }

    stage('Tests') {
      steps {
        sh 'sh ./scripts/test.sh'
      }
    }

    stage('Docker Image Build') {
      steps {
        script {
          docker.build "${env.DOCKER_IMAGE_TAG}"
        }

      }
    }

    stage('Docker Image Push') {
      steps {
        script {
          docker.push "${env.DOCKER_IMAGE_TAG}"
        }

      }
    }

  }
  environment {
    DOCKER_IMAGE_TAG = 'liljaylj/epam-task'
  }
}