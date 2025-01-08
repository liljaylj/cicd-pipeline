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
          app = docker.build "${env.DOCKER_IMAGE_TAG}"
        }

      }
    }

    stage('Docker Image Push') {
      steps {
        script {
          docker.withRegistry('https://registry.hub.docker.com', 'docker_creds')

          {
            app.push("${env.BUILD_NUMBER}")
            app.push('latest')
          }
        }

      }
    }

  }
  environment {
    DOCKER_IMAGE_TAG = 'liljaylj/epam-task'
  }
}