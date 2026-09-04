pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', 
                    url: 'https://github.com/thomas666-beast/hello-sh.git'
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'mkdir -p build'
                sh 'echo "Building..." > build/status.txt'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "All tests passed!" > test-results.txt'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'echo "Deployment complete!" > deploy.log'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline succeeded! 🎉'
        }
        failure {
            echo 'Pipeline failed! 😢'
        }
    }
}

