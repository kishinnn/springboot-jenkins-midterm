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
            // Jenkins confirmed the file is here: /var/jenkins_home/workspace/Midterm314/target/
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }   

}