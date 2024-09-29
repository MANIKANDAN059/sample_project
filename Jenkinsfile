pipeline{
    agent any

    stages {
        stage ('Checkout') {
            steps {
                git url: 'https://github.com/MANIKANDAN059/sample_project.git', branch: 'main'
            }
        }

        stage ('Run Tests') {
            steps {
                script {
                    if (isUnix()) {
                        sh 
                        '''
                        python --version
                        '''
                    } else {
                        bat
                        '''
                        python --version
                        '''
                    }
                }

            }
        }
    }
}