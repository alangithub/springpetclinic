pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image 'maven:latest' 
               }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Docker Build') {
            agent any
            steps {
               sh 'docker build -t shanem/spring-petclinic:latest .'
            }
        }
    }
}
