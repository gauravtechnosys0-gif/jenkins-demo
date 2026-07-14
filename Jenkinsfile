pipeline {

    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Repository already checked out by Jenkins'
            }
        }

        stage('Workspace') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy Successful'
            }
        }
    }
}
