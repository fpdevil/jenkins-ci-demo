pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:23-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo 'With Docker...'
                    ls -altr
                    npm -version
                    node --version
                    echo 'NPM: Install Packages & Build'
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Testing stage...'
            }
        }
    }
}
