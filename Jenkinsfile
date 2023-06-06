pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout ') {
      steps {
        git(url: 'https://github.com/sandy-7assan/node-docker-good-defaults.git', branch: 'main', changelog: true, poll: true)
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