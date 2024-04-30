node {
    stage('Cloner le dépôt') {
        // Cloner le dépôt Git
        checkout scm
    }

    stage('Copier le fichier') {
        // Copier le fichier sur le serveur de destination
        sshPublisher(
            publishers: [
                sshPublisherDesc(
                    configName: 'ubuntu',  // Assurez-vous que ceci correspond au nom de configuration SSH dans Jenkins
                    transfers: [
                        sshTransfer(
                            sourceFiles: 'index.html',
                            removePrefix: '',
                            remoteDirectory: '/',
                            execCommand: 'echo "Déploiement terminé"'
                        )
                    ]
                )
            ]
        )
    }
}
