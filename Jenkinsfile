pipeline {
  agent {dockerfile true}
  stages{
    stage ('Dockerfile') {
      steps{ 
sh 'gem install bundler'
sh 'cat <<-'PACKAGE_MANIFEST' > Gemfile'
sh 'source "https://rubygems.org"'
sh 'gem 'sinatra''
sh 'gem 'sinatra-contrib''
sh 'group :test do'
  sh 'gem 'rack-test''
  sh 'gem 'ci_reporter_test_unit''
sh 'end'
sh 'PACKAGE_MANIFEST'
sh 'bundle install'
      }
    }
  }
}
