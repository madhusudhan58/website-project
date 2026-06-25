pipeline {

    agent any

    stages {

        stage('Clone') {

            steps {

                git 'https://github.com/madhusudhan58/website-project.git'

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
                docker stop website || exit 0
                docker rm website || exit 0
                docker run -d --name website -p 8082:80 website-project
                '''
            }

        }

    }

}