pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn --version'
      }
    }
    stage('test') {
      steps {
        parallel(
          "test": {
            sh '''set -x
hostname
date
env | sort
pwd'''
            
          },
          "error": {
            echo 'FOO'
            
          }
        )
      }
    }
    stage('error') {
      steps {
        input(message: 'Continue?', id: 'do_continue')
      }
    }
  }
}