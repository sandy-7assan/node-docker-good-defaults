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
        sh 'docker build -t node:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name node -d -p 9229:9230 node:$BUILD_ID

'''
        sleep 3
        sh 'curl localhost:3000'
        sh 'docker stop node && docker rm node'
      }
    }

    stage('push') {
      steps {
        echo 'push'
      }
    }

  }
}