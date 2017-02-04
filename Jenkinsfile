pipeline {
    agent {
        docker { image 'node:6' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}
