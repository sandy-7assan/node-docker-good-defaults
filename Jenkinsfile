pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout ') {
      steps {
        echo 'checkout'
      }
    }

    stage('build') {
      steps {
        echo 'build'
      }
    }

    stage('run & test') {
      steps {
        echo 'run'
      }
    }

    stage('push') {
      steps {
        echo 'push'
      }
    }

  }
}