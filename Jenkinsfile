pipeline {
    agent any

    stages {

        stage('Build Maven Project') {
            steps {
                bat '''
                wsl mvn -f /home/kavya/projects/calculator-app/pom.xml clean install
                '''
            }
        }

    }

    post {

        success {

            // Copy jar from WSL to Jenkins workspace
            bat '''
            wsl cp /home/kavya/projects/calculator-app/target/*.jar /mnt/c/ProgramData/Jenkins/.jenkins/workspace/calculator-maven-pipeline/
            '''

            // Archive artifact in Jenkins
            archiveArtifacts artifacts: '*.jar'

            echo 'Build SUCCESS - Artifact archived'
        }

        failure {
            echo 'Build FAILED'
        }

    }
}