pipeline {
    agent any

    stages {
        stage('Install Packages for frontend') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Fix Issues in frontend') {
            steps {
                script {
                    sh 'npm audit fix'
                }
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