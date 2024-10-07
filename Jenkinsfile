pipeline{
    agent any
    environment {
        GITHUB_WEBHOOK_SECRET = credentials('github-webhook-secret')
    }
    stages {
        stage('Validate Webhook') {
            when {
                branch "main"
            }
            steps {
                script {
                    echo "Webhook Secret:"
                }
            }
        }

        stage ('Checkout') {
            when {
                branch "PR-*"
            }
            steps {
                git url: 'https://github.com/MANIKANDAN059/sample_project.git', 
                branch: 'main'
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
