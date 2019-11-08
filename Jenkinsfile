pipeline {
  agent any
  stages {
    stage('Build stage') {
      steps {
        script {
          mvnHome = tool 'M3'
          withEnv(["MVN_HOME=$mvnHome"]) {
            if (isUnix()) {
              sh '"$MVN_HOME/bin/mvn" clean compile'
            } else {
              bat(/"%MVN_HOME%\bin\mvn" clean compile/)
            }
          }
        }

      }
    }
    stage('Test Stage') {
      steps {
        script {
          mvnHome = tool 'M3'
          withEnv(["MVN_HOME=$mvnHome"]) {
            if (isUnix()) {
              sh '"$MVN_HOME/bin/mvn" test'
            } else {
              bat(/"%MVN_HOME%\bin\mvn" test/)
            }
          }
        }

      }
    }
  }
}