pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-nginx .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop cicd-container || true'
                sh 'docker rm cicd-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8083:80 --name cicd-container cicd-nginx'
            }
        }

    }
}
