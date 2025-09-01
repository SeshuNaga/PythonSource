pipeline {
    agent any
    stages{
        stage("Pull Git code"){
            steps{
                
                git branch : 'main'
                url : 'https://github.com/SeshuNaga/PythonSource.git'
            
            
        }
    }

    stages {
        stage('Created docker iamge') {
            steps{
                sh '/usr/local/bin/docker build -t python:latest .'
                sh '/usr/local/bin/docker run -d --name seshu python:latest'
            }
        }
    }
    
}