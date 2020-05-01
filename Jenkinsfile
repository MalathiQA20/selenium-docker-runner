pipeline{
    agent any
    stages{
        stage("Starting Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Running Tests"){
            steps{
                sh "docker-compose up searchmodule book-flight-module"
            }
        }
        stage("Bring Grid Down"){
            steps{
                sh "docker-compose down"
            }
        }
    }
}