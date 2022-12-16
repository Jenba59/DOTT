pipeline {
agent { docker { image 'ruby:3.0.0p0' } }
  stages {
    stage('requirements') {
      steps {
        sh 'gem install bundler'
      }
    }
    stage('build') {
      steps {
        sh 'bundle install'
      }
    }
    stage('test') {
      steps {
      }   
    }
  }
}
