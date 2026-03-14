pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/Aravindh-Cs/innovative.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t portfolio-image .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker stop portfolio-container || true'
                    sh 'docker rm portfolio-container || true'
                    sh 'docker run -d -p 3000:3000 --name portfolio-container portfolio-image'
                }
            }
        }

    }
}
