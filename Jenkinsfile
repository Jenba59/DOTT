pipeline {
  agent {dockerfile true}
  stages{
    stage ('Dockerfile') {
      steps{ 
          sh 'FROM cidr_convert_api'
          sh 'FROM ruby'       
          sh 'WORKDIR /app'
          sh 'COPY Gemfile.'
          sh 'RUN gem install bundler && bundle install'
          sh 'COPY . .'
          sh 'CMD ["ash", "-c", "ruby api.rb"]'
    }
  }
}
}
