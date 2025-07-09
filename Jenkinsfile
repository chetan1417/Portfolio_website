pipeline {
    agent any

    environment {
        IMAGE_NAME = "chetan1417/portfolio-website"
        IMAGE_TAG = "latest"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Skipping Git checkout (using local project folder)'
                // For GitHub: git url: 'https://github.com/your/repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}:${IMAGE_TAG}", '.')
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'dockerhub-creds', url: '']) {
                    script {
                        docker.image("${IMAGE_NAME}:${IMAGE_TAG}").push()
                    }
                }
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                script {
                    sh 'docker-compose down || true'
                    sh 'docker-compose up -d'
                }
            }
        }
    }
}
