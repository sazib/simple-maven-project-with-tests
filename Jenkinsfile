pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            withMaven(maven: 'M3') {
              sh 'mvn clean package'
            }

          }
        }
        stage('Results') {
          steps {
            junit 'tests/results/*.xml'
            archive 'target/*.jar'
          }
        }
      }
    }
  }
}
