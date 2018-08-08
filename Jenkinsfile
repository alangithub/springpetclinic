#!groovy

pipeline {
    agent none
    stages {
        stage('Back-end') {
            agent {
               docker { 
                  image '3.5-alphine'
               }
            }
            steps {
                sh 'mvn clean install'
            }
        }

    }
}
