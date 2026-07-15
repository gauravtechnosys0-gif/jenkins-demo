pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Workspace') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite:latest .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop website || true
                docker rm website || true

                docker run -d \
                  --name website \
                  -p 8085:80 \
                  mywebsite:latest
                '''
            }
        }
    }

    post {

        success {
            echo 'Deployment Successful!'
        }

        failure {
            echo 'Deployment Failed!'
        }

    }

}
