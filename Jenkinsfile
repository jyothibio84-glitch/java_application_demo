pipeline {
    agent any
    tools {
        maven 'Maven 3.10.0'
    }

    stages {
        stage('Check Out') {
            steps {
                // Use the git step to pull your repository directly in an inline script
                git branch: 'main', 
                    url: 'https://github.com/jyothibio84-glitch/java_application_demo.git'
            }
        }
        
        stage('Build') {
            steps {
                // Replace this echo with your actual build command (e.g., sh 'mvn clean install')
                sh 'mvn clean package'
            }
        }
    }
}
