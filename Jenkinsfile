#!groovy

pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image '3.5-jdk-8'
        }
      }
      steps {
        sh 'mvn clean install'
      }
    } 
  }
}
