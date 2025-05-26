pipeline {
    agent any

    environment {
        GO_VERSION = '1.24.0'
    }
    
    tools {
        go "${GO_VERSION}" 
    }

    triggers {
        githubPush()
    }
    
    options {
        buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '7', daysToKeepStr: '', numToKeepStr: '7')
    }

    stages {
        stage('Validate & Generate Code') {
            steps {
                // sh'go version'
            }
        }
    }

    post {
        always {
            cleanWs()
        }
        success {
            echo("All tests passed.");
        }
        failure {
            echo("Tests failed.");
        }
    }
}
