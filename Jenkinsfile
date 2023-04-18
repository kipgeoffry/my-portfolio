pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/kipgeoffry/my-portfolio', branch: 'master')
      }
    }

    stage('Log') {
      parallel {
        stage('log') {
          steps {
            sh 'echo "Hello World"'
            sh '''
                            echo "Multiline shell steps works too"
                            ls -lah
                            '''
          }
        }

        stage('view') {
          steps {
            sh 'whois kigen.ke'
          }
        }

      }
    }

    stage('Build') {
      steps {
        sh 'echo "The build id is ${BUILD_URL}"'
        sh 'echo "The build url is $BUILD_URL"'
      }
    }

    stage('Test') {
      steps {
        sh 'echo "Testing"'
        sh '''
                    ping 8.8.8.8 -c 4                    
                '''
        sh 'echo Test Completed'
      }
    }

  }
}