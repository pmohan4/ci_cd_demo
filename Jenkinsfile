pipeline {
  agent any
  stages {
    stage('Build Stage') {
      steps {
        script {
          mvn compile
        }

      }
    }
    stage('Test Stage') {
      steps {
        script {
          mvn test
        }

      }
    }
    stage('Deploy Stage') {
      steps {
        echo 'Deploy to Container'
      }
    }
  }
}