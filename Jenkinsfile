pipeline {
    agent {
        docker {
            image 'postman/newman:latest'
            args '-u root --entrypoint='
        }
    }
    stages {
        stage('Check version nodejs') {
            steps {
                sh 'newman --version'
                sh 'npm --version'
            }
        }
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
    post {
        success {
            // 1. Archive le rapport (téléchargeable depuis la page du build)
            archiveArtifacts artifacts: 'reports/*.html',allowEmptyArchive: true

        }
    }
}