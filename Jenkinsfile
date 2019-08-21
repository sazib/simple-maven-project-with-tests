pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            withMaven(maven: 'M3') {
              sh 'mvn clean install'
            }

          }
        }
        stage('Results') {
          steps {
            junit '**/target/surefire-results/TEST-*.xml'
            archiveArtifacts 'target/*.jar'
          }
        }
      }
    }
  }
}