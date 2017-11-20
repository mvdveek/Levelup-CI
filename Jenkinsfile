pipeline {
    agent any

    tools {
        maven 'M3'
        jdk 'JDK9'
    }

    
    stages {
        stage('Build') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn verify -Pintegrationtest'

            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                retry(3) {
                    echo 'Retrying....'
                }

                timeout(time: 3, unit: 'MINUTES') {
                    echo 'Waiting....'
                }
            }
        }
        
    }
    post {
          failure {
            echo 'Failure...'
          }
        }
}
