pipeline {
  agent none
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