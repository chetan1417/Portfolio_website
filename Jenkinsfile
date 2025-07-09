pipeline {
    agent any

    environment {
        GITHUB_TOKEN = credentials('github-token')
    }

    stages {
        stage('Build') {
            steps {
                echo 'No build required for static site.'
            }
        }

        stage('Deploy to GitHub Pages') {
            steps {
                script {
                    sh """
                        git config --global user.email "jenkins@localhost"
                        git config --global user.name "Jenkins CI"
                        git remote set-url origin https://chetan1417:${GITHUB_TOKEN}@github.com/chetan1417/Portfolio_website.git
                        git add .
                        git commit -m "Auto-deploy from Jenkins"
                        git push origin main
                    """
                }
            }
        }
    }
}
