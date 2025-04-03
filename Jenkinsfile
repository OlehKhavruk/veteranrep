pipeline {
    agent any

    environment {
        NODE_VERSION = "22.2.0"
    }

    stages {
        stage('Prepare') {
            steps {
                echo "Installing Node.js ${env.NODE_VERSION} using NVM"
                sh '''
                    export NVM_DIR="$HOME/.nvm"
                    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
                    . "$NVM_DIR/nvm.sh"
                    nvm install ${NODE_VERSION}
                    nvm use ${NODE_VERSION}
                    node -v
                '''
            }
        }

        stage('Build') {
            steps {
                sh '''
                    export NVM_DIR="$HOME/.nvm"
                    . "$NVM_DIR/nvm.sh"
                    nvm use ${NODE_VERSION}
                    npm -v
                '''
            }
        }

        stage('Test') {
            steps {
                echo "JENKINS_URL is $JENKINS_URL"
            }
        }
    }
}
