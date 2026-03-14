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
                bat 'docker run -d -p 3000:3000 --name portfolio-container portfolio-image'
            }
        }

    }
}
