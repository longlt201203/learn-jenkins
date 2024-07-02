pipeline {
    agent any

    stages {
        stage('Login Docker') {
            steps {
                echo 'Login with Docker...'
                sh """echo ${params.DOCKER_PASSWORD} | docker login -u ${params.DOCKER_USERNAME} --password-stdin"""
            }
        }
        
        stage('Build Docker') {
            steps {
                echo 'Building with Docker...'
                sh """docker build -t ${params.DOCKER_USERNAME}/learn-jenkins:latest ."""
            }
        }

        stage('Push Docker') {
            steps {
                echo 'Pushing with Docker...'
                sh """docker push ${params.DOCKER_USERNAME}/learn-jenkins:latest"""
            }
        }
    }
}