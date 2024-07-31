pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Test') {
      steps {
        echo 'Testing...'
        snykSecurity(
          snykInstallation: 'synk@latest' ,
          snykTokenId: 'synk-api-token' ,
          targetFile: 'app.py', // or your appropriate file if different
          failOnIssues: true // fail the build if vulnerabilities are found
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying...'
      }
    }
  }
}
