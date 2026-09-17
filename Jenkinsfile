pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Make sure to add your GitHub username/org and repository name
                git branch: 'main', url: 'https://github.com/tanp4577-web/-Parallel-Stages-Pipeline.git'
            }
        }
        stage('Parallel Checks') {
            parallel {
                stage('Frontend Check') {
                    steps {
                        bat 'python frontend_check.py'
                    }
                }
                stage('Backend Check') {
                    steps {
                        bat 'python backend_check.py'
                    }
                }
            }
        }
        stage('Summary') {
            steps {
                echo 'Both frontend and backend checks are complete.'
            }
        }
    }
}
