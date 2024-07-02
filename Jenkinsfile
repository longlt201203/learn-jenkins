pipeline {
    agent any

    environment {
        DOCKER_CREDENTIAL = credential('docker-credential')
    }

    stages {
        stage('Login Docker') {
            steps {
                echo 'Login with Docker...'
                sh 'echo $DOCKER_CREDENTIAL_PWD | docker login -u DOCKER_CREDENTIAL_USR --password-stdin'
            }
        }
        
        stage('Build Docker') {
            steps {
                echo 'Building with Docker...'
                sh 'docker build -t DOCKER_CREDENTIAL_USR/learn-jenkins:latest .'
            }
        }

        stage('Push Docker') {
            steps {
                echo 'Pushing with Docker...'
                sh 'docker push DOCKER_CREDENTIAL_USR/learn-jenkins:latest'
            }
        }
    }
}