pipeline {
    agent any

    stages {
        stage('Build Maven Project') {
            steps {
                bat 'wsl mvn -f /home/kavya/projects/calculator-app/pom.xml clean install'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}