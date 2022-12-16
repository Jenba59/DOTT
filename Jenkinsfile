pipeline {
  agent { docker { image 'ruby:2-alpine' } }
  stages {
    stage('requirements') {
      steps {
        sh 'gem install bundler -v 2.0.1'
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
