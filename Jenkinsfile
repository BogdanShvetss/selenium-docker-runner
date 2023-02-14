pipeline {
    agent any
    stages {
        stage("Run Tests") {
            bat "docker-compose up"
        }

        stage("Bring grid down") {
            bat "docker-compose down"
        }
    }
}