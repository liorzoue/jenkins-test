pipeline {
  agent {
    node {
      label 'net'
    }
    
  }
  stages {
    stage('Build dev') {
      parallel {
        stage('Build dev') {
          steps {
            powershell(script: 'test.ps', returnStatus: true)
          }
        }
        stage('Build Preprod') {
          steps {
            bat 'script.ps'
          }
        }
      }
    }
  }
}