pipeline {
    agent any

    tools {
        maven 'M3'
        jdk 'JDK1.8'
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
                timeout(time:5, unit:'DAYS') {
                     input message:'Approve deployment?'
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
