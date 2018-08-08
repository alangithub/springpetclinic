#!groovy

pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image 'maven:alphine'
               }
            }
            steps {
                sh 'mvn clean install'
            }
        }

    }
}
