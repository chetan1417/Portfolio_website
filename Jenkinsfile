pipeline {
    agent any

    environment {
        IMAGE_NAME = 'chetananeja/portfolio-website'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                bat "docker build -t %IMAGE_NAME% ."
            }
        }

        stage('Login & Push to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-cred', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    bat """
                        echo %DOCKERHUB_PASSWORD% | docker login -u %DOCKERHUB_USERNAME% --password-stdin
                        docker push %IMAGE_NAME%
                    """
                }
            }
        }
    }
}
