pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'node:lts-buster-slim'
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image(DOCKER_IMAGE).inside('-p 3000:3000') {
                        sh 'npm install'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    docker.image(DOCKER_IMAGE).inside {
                        sh 'npm test -- --watchAll=false'
                    }
                }
            }
        }
    }
}