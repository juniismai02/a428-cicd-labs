node {
    stage('Build') {
        docker.image('node:lts-buster-slim').inside('-p 3000:3000') {
            sh 'npm install'
        }
    }
    stage('Test') {
        docker.image('node:lts-buster-slim').inside {
            sh 'npm test'
        }
    }
}
