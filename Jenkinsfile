pipeline {
    agent {
        label 'docker-agent-alpine'
        }
    triggers{
        pollSCM '*/5****'
    }
    stages {
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
        stage('Build Docker Image'){
            steps{
                sh 'docker build -f my_third_project/Dockerfile . -t kipgeoffry/portfolio:latest'
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