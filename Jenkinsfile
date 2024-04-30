pipeline {
    agent any
    stages {
        stage('Cloner le dépôt') {
            steps {
                script {
                    echo "Cloning repository..."
                    git branch: 'main', url: 'https://github.com/PoPoGH/agile-devops.git'
                }
            }
        }
        stage('Construire Docker Image') {
            steps {
                script {
                    echo "Building Docker image..."
                    sh 'docker build -t monsite-html .'
                    echo "Docker build completed."
                }
            }
        }
        stage('Déployer sur le serveur') {
            steps {
                script {
                    echo "Deploying on server..."
                    sh 'docker run -d -p 80:80 monsite-html'
                    echo "Deployment completed."
                }
            }
        }
    }
}
