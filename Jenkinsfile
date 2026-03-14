pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t portfolio-image .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker stop portfolio-container || exit 0'
                bat 'docker rm portfolio-container || exit 0'
                bat 'docker run -d -p 8081:80 --name portfolio-container portfolio-image'
            }
        }

        stage('Open Website') {
            steps {
                bat 'timeout /t 5'
                bat 'start http://localhost:8081'
            }
        }

    }
}
