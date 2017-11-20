pipeline {
    agent any

    tools {
        maven 'M3'
        jdk 'JDK9'
    }

    
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        
    }
    post {
          failure {
            echo 'Failure...'
          }
        }
}
