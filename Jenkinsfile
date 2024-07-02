pipeline {
    agent any

    stages {
        stage('Login Docker') {
            env {
                DOCKER_USERNAME = params.DOCKER_USERNAME
                DOCKER_PASSWORD = params.DOCKER_PASSWORD
            }

            steps {
                echo 'Login with Docker...'
                sh "echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin"
            }
        }
        
        stage('Build Docker') {
            steps {
                echo 'Building with Docker...'
                sh "docker build -t $DOCKER_USERNAME/learn-jenkins:latest ."
            }
        }

        stage('Push Docker') {
            steps {
                echo 'Pushing with Docker...'
                sh """docker push $DOCKER_USERNAME/learn-jenkins:latest"""
            }
        }
    }
}