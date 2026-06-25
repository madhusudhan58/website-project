pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker') {
            steps {
                bat 'docker build -t website-project .'
            }
        }

        stage('Run Container') {
            steps {
                bat '''
                docker stop website
                docker rm website
                docker run -d -p 8081:80 --name website website-project
                '''
            }
        }
    }
}