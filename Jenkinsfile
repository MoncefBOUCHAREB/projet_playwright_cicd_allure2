pipeline {
    agent {
        docker {
            image 'mcp/playwright:latest'
            args '-u root --entrypoint='
        }
    }
    stages {
        stage('install dep') {
            steps {
                sh 'npm install'
            }
        }
        stage('Lancer le test test') {
            steps {
                sh ' npx playwright test'
            }
        }
    }
}