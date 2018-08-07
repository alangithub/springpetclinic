pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image 'image 'maven:latest' 
               }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Docker Build') {
            agent any
            steps {
               sh 'docker build -t alandockerhub/spring-petclinic:latest .'
            }
        }
    }
}
