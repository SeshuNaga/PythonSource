pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/SeshuNaga/ansibleForPythonProject.git'
            }
        }

        stage('Build Docker Image') {
            steps {
              sh 'docker build -t my-python-app .'
            }
        }
    }
}


