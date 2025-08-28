pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/samruddhi1902/devops-practice.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("myapp:${BUILD_NUMBER}")
                }
            }
        }
        stage('Run App') {
            steps {
                script {
                    sh 'docker run --rm myapp:${BUILD_NUMBER}'
                }
            }
        }
    }
}
