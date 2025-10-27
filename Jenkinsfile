pipeline {
    agent any

    triggers {
        cron('H/1 * * * *')
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code...'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Approval Stage') {
            steps {
                echo 'waiting for approval...'
                script {
                    def userInput = input(                       
                        message: "Do you want to proceed to deployment?",
                        ok: "Yes, proceed",
                        parameters: [
                            string(name: 'DEPLOY_ENV', defaultValue: 'No info given', description: 'Enter the deployment notes')
                        ]
                    )
                    echo "User input received: ${userInput}"
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post{
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
