pipeline {
  agent { dockerfile true }
  stages {
    stage ('version') {
      steps {
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
        sh 'Gemfile'
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
}
}
