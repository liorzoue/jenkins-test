pipeline {
  environment {
		BRANCH_NAME = "${scm.branches[0].name}"
  }
  
  agent { label 'net' }
  
  stages {
    stage('Build dev') {
      parallel {
        stage('Build dev') {
          steps {
            powershell(script: 'test.ps', returnStatus: true)
          }
        }
        stage('Build Preprod') {
          when {
            expression { env.BRANCH_NAME ==~ /.*(preprod).*/ }
          }
          steps {
            bat 'script.ps'
          }
        }
      }
    }
  }
}
