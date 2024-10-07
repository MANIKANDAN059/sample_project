pipeline{
    agent any

    environment {
        GITHUB_WEBHOOK_SECRET = credentials('github-webhook-secret')
    }

    stages {

        stage('Validate Webhook') {
            steps {
                script {
                    echo "Webhook Secret: ${GITHUB_WEBHOOK_SECRET}"
                }
            }
        }

        stage ('Checkout') {
            steps {
                git url: 'https://github.com/MANIKANDAN059/sample_project.git', 
                branch: 'main',
                credentialsId: 'github-webhook-secret'
            }
        }

        stage ('Run Tests') {
            when {
                branch 'PR-*'
            }
            steps {
                script {
                    if (isUnix()) {
                        sh
                        '''
                        python --version
                        echo "LINUX"
                        '''
                    } else {
                        bat
                        '''
                        python --version
                        echo "WINDOWS"
                        '''
                    }
                }

            }
        }
    }
}
