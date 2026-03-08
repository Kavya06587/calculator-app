pipeline {
    agent any

    stages {

        stage('Build Maven Project') {
            steps {
                bat 'mvn -U clean install'
            }
        }

    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar'
            echo "Build SUCCESS"
        }

        failure {
            echo "Build FAILED"
        }
    }
}