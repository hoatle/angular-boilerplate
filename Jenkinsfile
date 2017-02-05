#!groovy

pipeline {
    agent any
    parameters {
        string(name: 'DOCKER_IMAGE', defaultValue: 'hoatle/angular-boilerplate', description: 'The Docker image name to be build')
        string(name: 'DOCKER_USERNAME', defaultValue: 'hoatle', description: 'The username for the Docker registry')
        password(name: 'DOCKER_PASSWORD', description: 'The password the the Docker registry')
    }
    stages {
        stage('before_script') {
            steps {
                //sh 'cp .env.example .env'
                //sh 'export $(cat .env | grep -v ^# | xargs)'
                sh 'export CI_BUILD_TIME=$(date -u +"%Y-%m-%dT%H:%M:%SZ")'
                sh 'echo ${DOCKER_IMAGE}'
                sh 'echo $CI_BUILD_TIME'
                sh 'docker login -u=$DOCKER_USERNAME -p=$DOCKER_PASSWORD'
            }
        }
        stage('script') {
            steps {
                sh 'docker --version'
                sh 'docker-compose --version'
            }
        }
    }
}
