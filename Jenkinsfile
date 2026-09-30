pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/chowgulesonakshi-lab/cloud-ci-cd.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t cloud-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker rm -f cloud-app || true'
                sh 'docker run -d --name cloud-app -p 5000:5000 cloud-app'
            }
        }
    }
}