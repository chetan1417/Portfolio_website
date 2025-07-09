pipeline {
    agent {
        docker {
            image 'node:14'  // or any base image you need
        }
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    def customImage = docker.build("chetan1417/portfolio-website")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                echo 'Skipping actual push step for now.'
                // Add docker login and push commands here if needed
            }
        }
    }
}
