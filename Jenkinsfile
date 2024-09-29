pipeline{
    agent any

    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/MANIKANDAN059/sample_project.git', branch: 'main'
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
                        echo "MANI...."
                        '''
                    } else {
                        bat
                        '''
                        python --version
                        echo "MANI...."
                        '''
                    }
                }

            }
        }
    }
}
