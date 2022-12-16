pipeline {
  agent { docker { image 'ruby:2-alpine' } }
  stages {
    stage('requirements') {
      steps {
        sh 'gem install bundler -v 2.0.1'
      }
    }
    stage('Static Code Analysis-SonarCloud') {
      git 'https://github.com/Jenba59/DOTT.git'
    }
    stage('SonarCloud Analysis') {
                withSonarQubeEnv('SonarCloud') {
                    def scannerHome = tool 'SonarScanner 4.0';
                  withSonarQubeEnv('My SonarQube Server')
                  sh "${scannerHome} /bin/sonar-scanner
                }
    }
    stage('build') {
      steps {
        sh 'bundle install'
      }
    }
    stage ('CONVERT') {
      steps {
        sh 'ruby convert.rb'
      }
    }
    stage ('API') {
      steps {
        sh 'ruby api.rb'
      }
    }
    stage ('TESTS') {
      steps {
        sh 'ruby tests.rb'
      }
    }
  }
}
