pipeline{
    agent any

    stages{
        stage('Checkout'){
            steps{
                echo 'Checking out the code from sharanya branch...'
                checkout scm
            }
        }
        stage('Hello'){
            steps{
                echo 'Hello, World! from sharanya branch.'
            }       
        }
        stage('User Input'){
            steps{
                script {
                    input message: 'This is sharanya branch. Do you want to continue?', 
                    ok: 'Yes'
                }
            }
        }
        stage('Goodbye'){
            steps{
                echo 'Goodbye from sharanya branch.'
            }       
        }
    }

    post{
        always {
            echo 'This will always run after the pipeline completes.'
        }
    }
}





