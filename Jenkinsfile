pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('checkout ') {
      steps {
        echo 'hello'
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t app3:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name app3 -d -p 9229:9230 app3:$BUILD_ID

'''
        sleep 3
        sh 'curl localhost:9230'
        sh 'docker stop app3 && docker rm app3'
      }
    }

    stage('push') {
      steps {
        echo 'push'
      }
    }

  }
}