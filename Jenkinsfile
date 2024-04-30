pipeline {
    agent any
    stages {
        stage('Cloner le dépôt') {
            steps {
                git 'https://github.com/PoPoGH/agile-devops.git'
            }
        }
        stage('Construire Docker Image') {
            steps {
                sh 'docker build -t monsite-html .'
            }
        }
        stage('Déployer sur le serveur') {
            steps {
                sh 'docker run -d -p 80:80 monsite-html'
            }
        }
    }
}
