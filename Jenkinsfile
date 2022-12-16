pipeline {
  agent any
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
    stage ('Gemfile') {
      steps {
        sh 'ruby Gemfile'
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
