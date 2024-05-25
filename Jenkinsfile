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
        stage('Merge All Pull Requests') {
    steps {
        withCredentials([string(credentialsId: 'github-token', variable: 'GITHUB_TOKEN')]) {
            sh 'echo Merging all open Pull Requests...'
            sh '''
            # Đăng nhập GitHub CLI
            echo $GITHUB_TOKEN | gh auth login --with-token

            # Lấy danh sách tất cả các Pull Requests đang mở
            PRS=$(gh pr list --state open --json number -q '.[].number')

            # Kiểm tra nếu PRs không null
            if [ ! -z "$PRS" ]; then
                # Hợp nhất từng Pull Request
                for PR in $PRS; do
                    echo "Merging PR #$PR..."
                    gh pr merge --squash --delete-branch $PR
                done
            else
                echo "Không có Pull Request nào đang mở."
            fi
            '''
        }
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
