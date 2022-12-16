pipeline {
  agent {dockerfile true}
  stages{
    stage ('Dockerfile') {
      steps{ 
          sh 'gem install bundler'
          sh 'bundle install'     
          sh 'cp config/database-gitlab.yml config/database.yml'
          sh 'bundle exec rake db:create db:migrate RAILS_ENV=test'
          sh 'bundle exec rake test'
    }
  }
}
}
