pipeline{
    agent any
    environment {
        GITHUB_WEBHOOK_SECRET = credentials('github-webhook-secret')
    }
    stages {
        stage ('Checkout') {
            when {
                branch "PR-*"
            }
            steps {
                git url: 'https://github.com/MANIKANDAN059/sample_project.git', 
                branch: 'main'
            }
        }

        stage('Validate Webhook') {
            when {
                branch 'PR-*'
            }
            steps {
                script {
                    echo "Webhook Secret:"
                    echo "MANI:"
                }
            }
        }
    }
}
