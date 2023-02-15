pipeline {
    agent any
    stages {

        stage("Start grid") {
            steps {
                bat "docker-compose up -d hub chrome firefox"
            }
        }

        stage("Run Tests") {
            steps {
                bat "docker-compose up search-module1 book-flight-module1"
            }
        }

        steps {
            post {
               always {
                    archiveArtifacts artifacts: 'output/**'
                    bat "docker-compose down"
               }
            }
        }
    }
}