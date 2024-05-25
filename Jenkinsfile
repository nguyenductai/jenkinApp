pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/yourusername/ci-cd-demo.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building...'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Testing...'
                sh 'python -m unittest discover'
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
