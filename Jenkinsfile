pipeline {
  agent any
  stages {
    stage('Build stage') {
      steps {
        script {
          mvnHome = tool 'M3'
          withEnv(["MVN_HOME=$mvnHome"]) {
            if (isUnix()) {
              sh '"$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore clean package'
            } else {
              bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
            }
          }
        }

      }
    }
  }
}