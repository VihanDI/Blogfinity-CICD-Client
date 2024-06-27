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

        stage('Run frontend') {
            steps {
                script {
                    sh 'npm run dev'
                }
            }
        }

        stage('Test frontend') {
            steps {
                script {
                    sh 'curl http://localhost:5173'
                }
            }
        }

        stage('Cleanup') {
            steps {
                script {
                    sh 'pkill -f "node"'
                }
            }
        }
    }
}

tools {
    nodejs "nodejs"
}