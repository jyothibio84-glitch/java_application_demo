pipeline {
    agent any
    
    tools {
        maven 'Maven 3.10.0'
    }

    parameters {
        string(
            name: 'BRANCH_NAME', 
            defaultValue: 'main', 
            description: 'The Git branch you want to clone and build'
        )
        choice(
            name: 'MAVEN_GOAL', 
            choices: ['package', 'install', 'clean compile'], 
            description: 'Select the Maven lifecycle stage to run'
        )
    }

    stages {
        stage('Check Out') {
            steps {
                // Injected the BRANCH_NAME parameter securely using string interpolation
                git branch: "${params.BRANCH_NAME}", 
                    url: 'https://github.com/jyothibio84-glitch/java_application_demo.git'
            }
        }
        
        stage('Build') {
            steps {
                // Injected the MAVEN_GOAL parameter into your shell command
                sh "mvn clean ${params.MAVEN_GOAL}"
            }
        }
    }
}
