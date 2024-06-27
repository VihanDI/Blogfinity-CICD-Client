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
                sh 'sudo docker build -t inupavihan/blogfinity-frontend:%BUILD_NUMBER% .'
            }
        }
    }
}

tools {
    nodejs "nodejs"
}