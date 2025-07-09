pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Static site – no build step required.'
            }
        }

        stage('Test') {
            steps {
                echo 'No tests configured.'
            }
        }

        stage('Deploy to GitHub Pages') {
            steps {
                echo 'Deploying to GitHub Pages by committing to main branch.'
                sh '''
                    git config user.name "Jenkins CI"
                    git config user.email "jenkins@localhost"
                    git add .
                    git commit -m "Auto-deployed from Jenkins"
                    git push origin main
                '''
            }
        }
    }
}
