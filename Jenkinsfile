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
        parallel(
          "test": {
            sh '''set -x
hostname
date
env | sort
pwd'''
            
          },
          "": {
            echo 'FOO'
            
          }
        )
      }
    }
    stage('') {
      steps {
        input(message: 'Continue?', id: 'do_continue')
      }
    }
  }
}