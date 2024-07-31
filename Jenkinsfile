pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing...'
                snykSecurity(
                    snykInstallation: 'snyk@latest',
                    snykTokenId: 'snyk-api-token',  // Ensure this ID is correct
                    targetFile: 'requirements.txt', // Adjust as necessary
                    failOnIssues: true // Fail the build if vulnerabilities are found
                )
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Define Docker image name and tag
                    def imageName = 'my-app'
                    def imageTag = 'latest'
                    
                    // Build Docker image
                    docker.build("${imageName}:${imageTag}")
                }
            }
        }
    }
}
