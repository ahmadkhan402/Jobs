pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ahmadkhan402/Jobs.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'Ahmad402',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: 'var/www/html')],
                
                        )
                    ]
                )
            }
        }
    }
}
