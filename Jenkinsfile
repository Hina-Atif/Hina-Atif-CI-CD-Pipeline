pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Hina-Atif/Hina-Atif-CI-CD-Pipeline.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    def app = docker.build("hina-atif/ci-cd-pipeline")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker run -d -p 5000:5000 hina-atif/ci-cd-pipeline'
                }
            }
        }
    }
}
