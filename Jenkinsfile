pipeline {
  agent any
  stages {
    stage('Build stage') {
      steps {
        script {
          mvnHome = tool 'M3'
          mvn clean compile
        }

      }
    }
  }
}