cat <<-'JENKINSFILE' > Jenkinsfile
pipeline {
  agent { docker { image 'ruby:3.0.0' } }
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
        sh 'rake'
      }   
    }
  }
}
JENKINSFILE
