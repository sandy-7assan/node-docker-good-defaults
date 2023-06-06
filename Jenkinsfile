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
        sh 'docker build -t app2:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name app2 -d -p 9229:9230 app2:$BUILD_ID

'''
        sleep 3
        sh 'curl localhost:9229'
        sh 'docker stop app2 && docker rm app2'
      }
    }

    stage('push') {
      steps {
        echo 'push'
      }
    }

  }
}