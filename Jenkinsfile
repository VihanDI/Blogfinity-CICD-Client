pipeline {
    agent any

    stages {
        stage('Stop already running backend') {
            steps {  
                sh 'docker stop blogfinity-frontend-container'
            }
        }

        stage('Remove old container') {
            steps {  
                sh 'docker rm blogfinity-frontend-container'
            }
        }

        stage('Remove old Docker Image') {
            steps {  
                sh 'docker rmi inupavihan/blogfinity-frontend'
            }
        }

        stage('Clear builder cache') {
            steps {  
                sh 'docker builder prune -f'
            }
        }

        stage('Build Docker Image') {
            steps {  
                sh 'docker build -t inupavihan/blogfinity-frontend .'
            }
        }

        stage('Run Docker Image') {
            steps {  
                sh 'docker run -d -p 8081:5173 --name blogfinity-frontend-container inupavihan/blogfinity-frontend'
            }
        }
    }
}