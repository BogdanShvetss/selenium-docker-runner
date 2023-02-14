pipeline {
    agent any
    stages {
        stage("Run Tests") {
            steps {
                bat "docker-compose up"
            }
        }

        stage("Bring grid down") {
            steps {
                bat "docker-compose down"
            }
        }
    }
}