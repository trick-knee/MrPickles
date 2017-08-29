pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('test') {
      steps {
        sh 'mvn test'
        archiveArtifacts(artifacts: '**/*.?ar', allowEmptyArchive: true)
      }
    }
  }
}