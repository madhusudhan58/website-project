pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/madhusudhan58/website-project.git'
            }
        }

        stage('Build') {
            steps {
                bat 'docker build -t website-project:v1 .'
            }
        }

        stage('Push') {
            steps {
                bat 'docker push madhu58/website-project:v1'
            }
        }

        stage('Deploy') {
            steps {
                bat '''
                docker stop website || exit 0
                docker rm website || exit 0
                docker run -d --name website -p 8082:80 YOUR_DOCKER_USERNAME/website-project:v1
                '''
            }
        }

    }

}