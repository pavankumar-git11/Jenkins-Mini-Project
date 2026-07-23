pipeline {
    agent any

    environment {
        IMAGE_NAME = "pavankumar11docker/docker-mini-project"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/pavankumar-git11/Docker-Mini-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat "docker build -t %IMAGE_NAME% ."
            }
        }

        stage('Login to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {

                    bat 'echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                bat "docker push %IMAGE_NAME%"
            }
        }

        stage('Deploy Application') {
            steps {
                bat "docker compose up -d"
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }

        failure {
            echo "Pipeline execution failed!"
        }
    }
}