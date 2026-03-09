pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cicd-nginx .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8083:80 cicd-nginx'
            }
        }

    }
}
