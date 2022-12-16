pipeline {
  agent { docker { image 'ruby:2-alpine' } }
  stages {
    stage('requirements') {
      steps {
        sh 'gem install bundler -v 2.0.1'
      }
    }
    stage('Static Code Analysis SonarCloud') {
      steps {
                withSonarQubeEnv('SonarCloud') {
                    sh '''${scannerHome}/bin/sonar-scanner \
                        -Dsonar.organization=Jenba59 \
                        -Dsonar.projectKey=PONDIO \
                        -Dsonar.sources=./cidr_convert_api/ruby/ \
                        -Dsonar.host.url=https://sonarcloud.io
                    '''
                }
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
