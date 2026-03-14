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
                echo 'Building the fat jar artifact...'
        	sh 'mvn clean package'
            }
        }
    }
    post {
        always {
            // Update this line to match where Jenkins found the file
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }    

}