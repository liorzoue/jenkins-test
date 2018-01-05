pipeline {
  agent any
  stages {
    stage('Build dev') {
      steps {
        powershell(script: 'test.ps', returnStatus: true)
      }
    }
  }
}