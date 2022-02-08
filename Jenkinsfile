pipeline {
    agent any
    stages {
        stage('Test Junit') {
            steps {
                sh 'mvn clean test'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d --build'
            }
        }
        stage('Test Integration') {
            steps {
                sh 'wget -m http://localhost:8085/app-web-demo/'
            }
        }
    }
}