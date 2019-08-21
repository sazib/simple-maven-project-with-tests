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
            junit '**/target/surefire-reports/TEST-*.xml'
            archive 'target/*.jar'
          }
        }
      }
    }
  }
}
