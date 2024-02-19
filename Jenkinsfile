pipeline {
    agent any 
    stages {
        stage('Preparation') { 
            steps {
                sh "rm -rf my-app || true" // Ensure the workspace is clean
            }
        }
        stage('clone repo and clean') { 
            steps {
                sh "git clone https://github.com/RAulshodmonbekov1107/my-app.git"
                sh "cd my-app && ./mvnw clean" // Use the Maven wrapper to clean the project
            }
        }
        stage('Test') { 
            steps {
                sh "cd my-app && ./mvnw test" // Use the Maven wrapper to run tests
            }
        }
        stage('Deploy') { 
            steps {
                sh "cd my-app && ./mvnw package" // Use the Maven wrapper to package the application
            }
        }
    }
}

