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
        sh 'docker build -t node1:$BUILD_ID .'
      }
    }

    stage('run & test') {
      steps {
        sh '''docker run --name node1 -d -p 9229:9230 node1:$BUILD_ID

'''
        sleep 3
        sh 'curl localhost:8080'
        sh 'docker stop node1 && docker rm node1'
      }
    }

    stage('push') {
      steps {
        sh 'docker tag node1:$BUILD_ID sarhanmo/node:$BUILD_ID'
        sh 'docker login -u sarhanmo -p Mohammad-99'
        sh 'docker push sarhanmo/node:$BUILD_ID'
      }
    }

  }
}