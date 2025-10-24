pipeline {
    agent any

    stages {
        stage('pull source code') {
            steps {
                git branch: 'main', url: 'https://github.com/riskaadi/e-voting-app.git'
            }
        }
        stage('build container image') {
            steps {
                sh 'docker compose build'
            }
        }
         stage('deploy container app') {
            steps {
                sh 'docker compose up -d'
            }
        }
        stage('push image') {
            steps {
                sh 'docker compose push'
            }
        }
    }
}
