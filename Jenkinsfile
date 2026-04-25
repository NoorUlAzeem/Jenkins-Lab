pipeline {
    agent any
    
    // 1. Define our Parameters (The Checkbox)
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Check to run the Test stage')
    }
    
    // 2. Define our Build Tools
    tools {
        maven 'Maven3' // This matches the name you just created in Jenkins!
    }
    
    environment {
        VERSION_NUMBER = '1.0.0'
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Building Version: ${VERSION_NUMBER}"
                // A safe Windows command to prove Maven is loaded:
                bat 'mvn --version' 
            }
        }
        stage('Test') {
            // 3. The Conditional Rule (Only run if the box is checked)
            when {
                expression { return params.executeTests }
            }
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
    
    post {
        always {
            echo 'POST BUILD ACTION: Pipeline finished!'
        }
    }
}
