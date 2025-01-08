pipeline {
  agent {
    docker {
      image 'node:lts-slim'
    }

  }
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
          docker.build 'liljaylj/epam-task'
        }

      }
    }

  }
}