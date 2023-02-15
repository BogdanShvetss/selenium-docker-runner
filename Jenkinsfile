pipeline {
    agent any
    stages {
        stage("Pull latest image") {
            steps {
                bat "docker pull bohdanshvets/selenium-docker"
            }
        }

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
    }

    post {
        always {
            archiveArtifacts artifacts: 'output/**'
            bat "docker-compose down"
        }
    }
}