#!groovy

pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image 'maven:3.5.0'
                  args '-v maven-repo:/root/.m2'
               }
            }
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Docker Build') {
            agent any
            steps {
               sh 'docker build -t alandockerhub/spring-petclinic:latest .'
            }
        }

        stage('Docker Push') {
            agent any
            steps {
               withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                  sh 'docker login -u="$DOCKER_USERNAME" -p="$DOCKER_PASSWORD"'
                  sh 'docker push alandockerhub/spring-petclinic:latest'  
               }
            }
        }

    }
}



