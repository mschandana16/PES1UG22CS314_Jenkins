pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o PES1UG22CS314-1 PES1UG22CS314.cpp' // Compile the C++ file
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './PES1UG22CS314-1' // Run the compiled program
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying application...' 
                // Add deployment steps here if needed
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed! Please check the logs.'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
    }
}
