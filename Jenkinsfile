pipeline {
    agent any

     environment {
        GITHUB_TOKEN = credentials('github-token') // Use the actual ID of your GitHub token
       // Use the actual ID of your Heroku API key
    }

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
