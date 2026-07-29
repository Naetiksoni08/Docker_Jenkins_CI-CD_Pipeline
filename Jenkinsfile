pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                dir('docker-jenkins-demo') {
                    sh 'chmod +x mvnw'
                    sh './mvnw clean package -DskipTests'
                }
            }
        }

        stage('Docker Build') {
            steps {
                dir('docker-jenkins-demo') {
                    sh 'docker build -t docker-jenkins-demo .'
                }
            }
        }
    }
}