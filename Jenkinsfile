pipeline {
    agent any

    environment {
        REGISTRY = "127.0.0.1:8083"
        APP_NAME = "afo/ke/prod/bulk-upload-service"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/SeshuNaga/PythonSource.git'
            }
        }

        stage('Read Version') {
            steps {
                script {
                    // Example: if you have a VERSION file in repo
                    VERSION = readFile('version').trim()

                   

                    echo "Using version: ${VERSION}"
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                docker build -t $REGISTRY/$APP_NAME:$VERSION .
                '''
            }
        }

        stage('Push Docker Image') {
            steps {
                sh '''
                docker push $REGISTRY/$APP_NAME:$VERSION
                '''
            }
        }
    }
}
