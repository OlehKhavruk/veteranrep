pipeline {
    agent any

    environment {
        NODE_VERSION = "22"
    }

    stages {
        stage('Prepare') {
            steps {
                echo "Installing Node.js version ${env.NODE_VERSION}"
                sh '''
                    curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION}.x | sudo -E bash -
                    sudo apt-get install -y nodejs
                    node -v
                '''
            }
        }

        stage('Build') {
            steps {
                echo "Simulating build process"
                sh 'npm -v'
            }
        }

        stage('Test') {
            steps {
                echo "Simulating test process"
                sh 'echo $JENKINS_URL'
            }
        }
    }
}
