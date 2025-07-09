pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/chetan1417/Portfolio_website.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step required for static portfolio project.'
            }
        }

        stage('Test') {
            steps {
                echo 'Skipping tests (none present).'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Ready for deployment (add logic when ready).'
            }
        }
    }
}
