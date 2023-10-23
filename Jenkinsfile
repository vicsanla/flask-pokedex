pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "docker build -t vicsanla/pokedex-flask:${env.BUILD_NUMBER} ."
            }
        }
    }
}
