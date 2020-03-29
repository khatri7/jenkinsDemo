pipeline{
    
    agent any
    
    tools{
        maven "MAVEN_HOME"
    }
    
    stages{
        stage('Build'){
            steps{
                git "https://github.com/khatri7/jenkinsDemo.git"
                bat "mvn clean compile"
            }
        }
        stage('Test'){
            steps{
                bat "mvn test"
            }
        }
        stage('Report'){
            steps{
                allure includeProperties: false, jdk: 'Default', results: [[path: 'allure-results']]
            }
        }
    }
}
