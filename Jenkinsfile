pipeline {
  agent {dockerfile true}
  stages{
    stage ('Dockerfile') {
      steps{
          sh 'FROM ruby 3.0.0p0'
          sh 'WORKDIR /app'
          sh 'COPY Gemfile.'
          sh 'RUN gem install bundler && bundle install'
          sh 'COPY . .'
          sh 'CMD ["ash", "-c", "ruby api.rb"]'
      }
    }
  }
}
