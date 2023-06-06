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
        sh 'docker build -t jenkins:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name jenkins -d -p 3000:3000 jenkins:$BUILD_ID

'''
        sleep 3
        sh 'curl localhost:3000'
        sh 'docker stop jenkins && docker rm jenkins'
      }
    }

    stage('push') {
      steps {
        echo 'push'
      }
    }

  }
}