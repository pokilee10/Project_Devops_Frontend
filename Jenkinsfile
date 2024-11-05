pipeline {
    agent any
    stages {
        stage('Clone Stage') {
            steps {
                git branch: 'main', url: 'https://github.com/pokilee10/Project_Devops_Frontend.git'
            }
        }
        stage('Build and Push Image Stage') {
            steps {
                withDockerRegistry(credentialsId: 'docker_hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t pokilee10/project_devops_frontend:latest .'
                    sh 'docker push pokilee10/project_devops_frontend:latest'
                }
            }
        }
    }
}