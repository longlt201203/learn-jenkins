pipeline {
    agent any

    stages {
        stage('Login Docker') {
            echo 'Login with Docker...'
            echo $DOCKER_PASSWORD
            sh 'docker login -u $DOCKER_USERNAME --password-stdin'
        }
        
        stage('Build Docker') {
            steps {
                echo 'Building with Docker...'
                sh 'docker build -t longthanhle1122/learn-jenkins:latest .'
            }
        }

        stage('Push Docker') {
            steps {
                echo 'Pushing with Docker...'
                sh 'docker push longthanhle1122/learn-jenkins:latest'
            }
        }
    }
}