pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/nguyenductai/jenkinApp', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building...'
               
            }
        }

        stage('Test') {
            steps {
                sh 'echo Testing...'
               
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo Deploying...'
                // Add your deployment steps here
            }
        }
    }
}
