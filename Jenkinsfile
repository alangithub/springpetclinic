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
    }
}
