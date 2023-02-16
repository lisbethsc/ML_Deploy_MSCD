pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                echo 'Checkout code...'
            }
        }
        stage('Checkout'){
            steps{
                sh "tox -e train"
            }
        }
        stage('Build'){
            steps{
                echo 'Building the code...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying to test...'
            }
        }
    }
}