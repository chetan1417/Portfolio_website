pipeline {
    agent any

    environment {
        GIT_CREDENTIALS_ID = 'chetan1417'
    }

    stages {
        stage('Build') {
            steps {
                echo 'No build step needed for static portfolio website.'
            }
        }

        stage('Deploy to GitHub Pages') {
            steps {
                withCredentials([usernamePassword(credentialsId: "${GIT_CREDENTIALS_ID}", usernameVariable: 'GIT_USERNAME', passwordVariable: 'GIT_PASSWORD')]) {
                    bat '''
                        git config --global user.name "Jenkins CI"
                        git config --global user.email "jenkins@localhost"
                        git remote set-url origin https://%GIT_USERNAME%:%GIT_PASSWORD%@github.com/chetan1417/Portfolio_website.git
                        git add .
                        git commit -m "Auto-deploy from Jenkins"
                        git push origin main
                    '''
                }
            }
        }
    }
}
