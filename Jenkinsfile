pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-credentials')
    }
    
    stages {
        stage('Build Docker Image') {
            steps {
                sh "docker build -t jenkin:latest ."
            }
        }
        
        stage('Push Docker Image to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', passwordVariable: 'DOCKERHUB_CREDENTIALS_PSW', usernameVariable: 'DOCKERHUB_CREDENTIALS_USR')]) {
    sh "docker login -u ${env.DOCKERHUB_CREDENTIALS_USR} -p ${env.DOCKERHUB_CREDENTIALS_PSW} https://hub.docker.com/repository/docker/pavanvc/jenkin/general"
            }
                sh "docker push jenkin:latest"
                }
            }
        
    }
    
    post {
        success {
            echo 'Docker image build and push successful'
        }
        failure {
            echo 'Docker image build or push failed'
        }
    }
}
