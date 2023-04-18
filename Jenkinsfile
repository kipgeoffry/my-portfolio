pipeline {
  agent any
  stages {
    stage('Code checkout') {
      steps {
        sh 'git clone https://github.com/kipgeoffry/my-portfolio.git'
      }
    }

    stage('log') {
      steps {
        sh 'echo \'Checking if all is well\''
      }
    }

  }
}