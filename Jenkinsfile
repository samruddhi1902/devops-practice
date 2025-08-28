pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/samruddhi1902/devops-practice.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image and tag with build number
                    def myImage = docker.build("myapp:${BUILD_NUMBER}")
                }
            }
        }

        stage('Run App') {
            steps {
                script {
                    // Run the Docker image
                    docker.image("myapp:${BUILD_NUMBER}").run("-p 3000:3000 --rm")
                }
            }
        }
    }
}
