pipeline {
    agent {
        any
    }
    triggers{
        pollSCM '*/2 * * * *'
    }
   
    stages {
        stage('checkout code'){
            steps{
                sh 'echo pulling code from Github'
                git(url:'https://github.com/kipgeoffry/my-portfolio', branch: 'master')
            }
        }
        stage('Log') {
            parallel{
                stage('log'){
                    steps {
                        sh 'echo "Hello World"'
                        sh '''
                            echo "Multiline shell steps works too"
                            ls -lah
                            '''
                        }
                }
                stage('view'){
                    steps{
                        sh 'whois kigen.ke '
                    }
                }
            }
        }    
        stage('run docker'){
            steps{
                sh 'docker ps -a'
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
