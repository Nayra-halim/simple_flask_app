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
