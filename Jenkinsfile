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
                error 'Forcing a failure to test email'
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
                subject: "Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}",
                body: """
                    Build Status: ${currentBuild.currentResult}
                    Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed.
                    Full details: ${env.BUILD_URL}
                """,
                attachLog: true
            )
        }
    }
}
