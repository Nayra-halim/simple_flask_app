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
            snykInstallation: 'snyk@latest',
            snykTokenId: 'synk-new',  // Ensure this is a valid credential ID
            targetFile: 'requirements.txt', // Use the appropriate file for your dependencies
            failOnIssues: true // Fail the build if vulnerabilities are found
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
