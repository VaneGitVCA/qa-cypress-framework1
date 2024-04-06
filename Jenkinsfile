pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main',
                        url: 'https://github.com/VaneGitVCA/qa-cypress-framework1'
                }
            }
        }
        stage('Install dependencies') {
            steps {
                script {
                    bat 'npm install'
                }
            }
        }
        stage('Run tests') {
            steps {
                script {
                    bat 'npm run cy:run-ci'
                }
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'cypress/reports/**'
        }
    }
}