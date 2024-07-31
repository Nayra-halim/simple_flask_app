pipeline {
  agent { dockerfile true }
  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }
    stage('Build Docker Image') {
      steps {
          script {
              def imageName = 'my-app'
              def imageTag = 'latest'
              docker.build("${imageName}:${imageTag}")
                }
            }
        }
    stage('Test') {
    steps {
        echo 'Testing...'
        snykSecurity(
            snykInstallation: 'snyk@latest',
            snykTokenId: 'synk-new',
            targetFile: 'simple_flask_app', // Use the appropriate file for your dependencies
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
