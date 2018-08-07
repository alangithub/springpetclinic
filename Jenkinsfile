pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image 'maven:3.5.0'
               }
            }
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Docker Build') {
            agent any
            steps {
               sh 'docker build -t shanem/spring-petclinic:latest .'
            }
        }

        stage('Docker Push') {
            agent any
            steps {
               withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
                  sh 'docker push alandockerhub/spring-petclinic:latest'  
            }
    }
}
