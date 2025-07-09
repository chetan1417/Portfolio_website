pipeline {
    agent any  // or use: label 'your-agent-label'

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-cred')
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = sh(script: 'docker build -t chetan1417/portfolio-website .', returnStdout: true)
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    sh """
                        echo "${DOCKERHUB_CREDENTIALS_PSW}" | docker login -u "${DOCKERHUB_CREDENTIALS_USR}" --password-stdin
                        docker push chetan1417/portfolio-website
                    """
                }
            }
        }
    }
}
