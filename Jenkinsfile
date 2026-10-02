@Library ('java-shared-lib') _
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
        string(
             name: 'Git_URL', 
            defaultValue: 'https://github.com/jyothibio84-glitch/java_application_demo.git', 
            description: 'The Git url you want to clone and build'
        )
    }

    stages {
        stage('Check Out') {
            steps {
              gitcheckout(
                  branch: "${params.BRANCH_NAME}",
                    url: "${params.Git_URL}"
              )
            }
        }
        
        stage('Build') {
            steps {
              runmaven(
                    goal: "${params.MAVEN_GOAL}"
                )
            }
        }
    }
}
