pipeline {
    agent any

    environment {
        REGISTRY = "localhost:5000"
        IMAGE_NAME = "my-python-app"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SeshuNaga/PythonSource.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${IMAGE_NAME}:latest ."
                }
            }
        }

        stage('Tag Image for Local Registry') {
            steps {
                script {
                    sh "docker tag ${IMAGE_NAME}:latest ${REGISTRY}/${IMAGE_NAME}:latest"
                }
            }
        }

        stage('Push to Local Registry') {
            steps {
                script {
                    sh "docker push ${REGISTRY}/${IMAGE_NAME}:latest"
                }
            }
        }
    }
}
