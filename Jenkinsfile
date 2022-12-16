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
    agent {dockerfile true}
    stage ('Dockerfile') {
      steps {
        FROM ruby:2-alpine

WORKDIR /app

COPY Gemfile .
RUN gem install bundler \
    && bundle install

COPY . .
CMD ["ash", "-c", "ruby api.rb"]
# docker build -t rbm .
# docker run -ti -p 8000:8000 rbm
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
