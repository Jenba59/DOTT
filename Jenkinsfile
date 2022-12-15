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
    stage ('convert') {
      steps {
        sh 'ruby convert.rb'
      }
    }
    stage ('Return') {
      steps {
        sh 'ruby api.rb'
      }
    }
    stage ('Tests') {
      steps {
        sh 'ruby tests.rb'
      }
     }
    }
   } 
  }
 }
}
