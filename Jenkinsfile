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
        sh 'Gemfile.rb'
      }
    }
    stage ('API') {
      steps {
        sh 'api.rb'
      }
    }
    stage ('CONVERT') {
      steps {
        sh 'convert.rb'
      }
    }
     stage ('TESTS') {
      steps {
        sh 'tests.rb'
      }
    }
  }
}
