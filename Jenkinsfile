pipeline {
  agent {
    dockerfile true
  }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Build Docker Image') {
      steps {
          echo 'flask version'
            }
        }
    stage('Test') {
    steps {
        echo 'Testing...'
        snykSecurity(
            snykInstallation: 'snyk@latest',
            snykTokenId: 'synk-new',
            targetFile: 'simple_flask_app', 
            failOnIssues: true 
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
