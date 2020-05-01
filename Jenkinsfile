pipeline{
    agent any
    stages{
        stage("Pulling latest image"){
            steps{
                sh "docker pull malathiqe/selenium-docker"
            }

        }
        stage("Starting Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Running Tests"){
            steps{
                sh "docker-compose up searchmodule1 book-flight-module1"
            }
        }
    }
    post{
        always{
            archiveArtifacts artifacts: 'output/**'
            sh "docker-compose down"
        }
    }
}