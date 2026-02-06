pipeline {
    agent any

    stages {
        stage('without docker') {
            steps {
                sh '''
                echo "Jenkins without Docker"
                touch container-no.txt
                ls -la
                '''
            }
        }
        
        stage('with docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps{
                sh '''
                echo "Jenkins with Docker"
                touch container-yes.txt
                ls -la
                '''
            }
        }
    }
}
