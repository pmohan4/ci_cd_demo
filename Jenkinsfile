pipeline {
  agent any
  stages {
    stage('Build Stage') {
      steps {
        script {
          checkout(scm)
          mvnHome = tool 'M3'
        }

      }
    }
    stage('Test Stage') {
      steps {
        script {
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
    stage('Deploy Stage') {
      steps {
        echo 'Deploy Stage'
      }
    }
  }
}