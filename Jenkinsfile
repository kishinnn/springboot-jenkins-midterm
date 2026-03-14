pipeline {
    agent any // This allows the build to run on any available Jenkins agent

    stages {
        stage('Checkout') {
            steps {
                // This pulls your code from the GitHub repository you configured
                checkout scm 
            }
        }
        stage('Build') {
            steps {
                echo 'Building the fat jar...'
                // This command uses the Maven wrapper to package your Java project
                // It creates the .jar file required for your midterm
                sh './mvnw clean package' 
            }
        }
    }
    post {
        success {
            // This archives the resulting jar file so you can see it in Jenkins
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}