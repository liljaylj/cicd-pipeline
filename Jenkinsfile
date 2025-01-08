pipeline {
  agent {
    docker {
      image 'node:lts-slim'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'sh ./scripts/build.sh'
      }
    }

    stage('Test') {
      steps {
        sh 'sh ./scripts/test.sh'
      }
    }

    stage('') {
      steps {
        sh 'docker build -t liljaylj/practical-task'
      }
    }

  }
}