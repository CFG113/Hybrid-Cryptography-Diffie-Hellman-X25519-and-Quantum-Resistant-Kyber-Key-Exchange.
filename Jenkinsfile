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
                subject: "Jenkins Pipeline Status: ${currentBuild.fullDisplayName}",
                body: """
                    <p>Build Status: ${currentBuild.currentResult}</p>
                    <p>Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' has completed.</p>
                    <p>Check the console output here: ${env.BUILD_URL}</p>
                """,
                mimeType: 'text/html',
                attachLog: true
            )
        }
    }
}
