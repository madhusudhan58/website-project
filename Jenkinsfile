pipeline {
    agent any

    stages {

        stage('Build Docker') {
            steps {
                bat 'docker build -t website-project .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 8081:80 --name website website-project'
            }
        }

    }
}
