pipeline {
    agent any
    
    tools {
        maven 'Maven 3' 
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Change 'midterm-springboot' to the exact name of your project folder
                dir('midterm-springboot') { 
                    echo 'Building the fat jar artifact...'
                    sh 'mvn clean package' 
                }
            }
        }
    }
    post {
        always {
            // Updated path to find the jar inside the subfolder
            archiveArtifacts artifacts: 'midterm-springboot/target/*.jar', fingerprint: true
        }
    }
}