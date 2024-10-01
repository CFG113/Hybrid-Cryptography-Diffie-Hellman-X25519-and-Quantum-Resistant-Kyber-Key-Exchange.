pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build App'
            }
        }

        stage('Test') {
            steps {
                echo 'Test App'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy App'
            }
        }
    }

    post {
        always {
            emailext body: '${BUILD_STATUS}: The Jenkins Pipeline has finished successfully.', subject: 'Pipeline Status', to: 'christianghantous1@gmail.com'
        }
    }
}
