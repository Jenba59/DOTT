pipeline {
  agent { docker { image 'ruby:2-alpine' } }
  stages {
    stage('requirements') {
      steps {
        sh 'gem install bundler -v 2.0.1'
      }
    }
    stage('build') {
      steps {
        sh 'bundle install'
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
