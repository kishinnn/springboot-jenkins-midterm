pipeline {
    agent any
    
    tools {
        // This tells Jenkins to use a Maven installation it already has
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
                echo 'Building the fat jar artifact...'
                // Using 'mvn' directly instead of './mvnw'
                sh 'mvn clean package' 
            }
        }
    }
    post {
        always {
            // This captures the .jar file for your screenshot requirement
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}