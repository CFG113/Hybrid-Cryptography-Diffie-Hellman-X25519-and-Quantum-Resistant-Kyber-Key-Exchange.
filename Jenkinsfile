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
            emailext(
                to: 'christianghantous1@gmail.com',
                subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                body: """
                    Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL}) 
                    completed with status: ${currentBuild.currentResult}.
                """,
                attachLog: true
            )
        }
    }
}
