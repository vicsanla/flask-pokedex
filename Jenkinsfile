pipeline {
    agent any
    environment{
        DOCKERHUB_CREDENCIALS = credentials ('dockerhub')
        RepoDockerHub = 'zdenkoo98'
        NameContainer = 'pokedex-flask'
    }

    stages {
        stage('Build'){
            steps{
                sh "docker build -t ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ."
            }
        }

        stage('Login to Dockerhub'){
            steps{
                sh "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u $DOCKERHUB_CREDENCIALS_USR --password-stdin "
            }
        }

        stage('Push image to Dockerhub'){
            steps{
                sh "docker push ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} "
            }
        }

        //stage('Stop container') {
        //    steps{
        //        sh "docker stop ${env.NameContainer}"
        //    }
        //}
//
        //stage('Delete container') {
        //    steps{
        //        sh "docker rm ${env.NameContainer}"
        //    }
        //}
//
        //stage('Deploy container'){
        //    steps{
        //        sh "docker run -d --name ${env.NameContainer} -p 5000:5000 ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER}"
        //    }
        //}
        //
        //stage('Docker logout'){
        //    steps{
        //        sh "docker logout"
        //    }
        //}
    }
}