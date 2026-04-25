pipeline {
    agent any
    
    // This is the Environment Variable section
    environment {
        VERSION_NUMBER = '1.0.0'
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Building Version: ${VERSION_NUMBER}"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    
    // This is the Post Build Actions section
    post {
        always {
            echo 'POST BUILD ACTION: This will always run at the end!'
        }
        success {
            echo 'POST BUILD ACTION: The pipeline was a success!'
        }
    }
}
