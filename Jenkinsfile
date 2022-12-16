pipeline {
  agent any
  agent {dockerfile true}
  stages {
    stage ('version') {
      steps {
        sh 'ruby --version'
      }
    }
    stage ('hello') {
      steps {
        sh 'ruby Hello.rb'
      }
    }
    stage ('Dockerfile') {
      steps {
        sh 'Dockerfile'
      }
    }
    stage ('API') {
      steps {
        sh 'ruby api.rb'
      }
    }
    stage ('CONVERT') {
      steps {
        sh 'ruby convert.rb'
      }
    }
     stage ('TESTS') {
      steps {
        sh 'ruby tests.rb'
      }
    }
  }
}
