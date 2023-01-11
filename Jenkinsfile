pipeline {
    agent any
    environment{
 //       ServerDeploy="192.168.0.17"
 //       DOCKERHUB_CREDENCIALS = credentials ('credencials-dockerhub')
        RepoDockerHub = 'zdenkoo98'
        NameContainer = 'nodeapp_parcial'
    }

    stages {
        stage('Build'){
            steps{
                sh "docker build -t ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ."
            }
        }

 //       stage('Login to Dockerhub'){
 //           steps{
 //               sh "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u $DOCKERHUB_CREDENCIALS_USR //--password-stdin "
 //           }
  //      }

 //       stage('Push image to Dockerhub'){
 //           steps{
 //               sh "docker push ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} "
 //           }
 //       }


  //      stage('Deploy to DEV'){
  //          steps{
  //              script{
  //                  def remote = [:]
  //                  remote.name = 'dev'
  //                  remote.host = "${env.ServerDeploy}"
  //                  remote.allowAnyHosts = true
  //                  withCredentials([sshUserPrivateKey(credentialsId: 'sshUser-key', keyFileVariable: //'identity', passphraseVariable: 'passphrase', usernameVariable: 'userName')]) {
  //                  remote.user = userName
  //                  remote.identityFile = identity
  //                  remote.passphrase = passphrase
//// LOGIN DOCKERHUB
//                    writeFile file: 'login.sh', text: "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u //$DOCKERHUB_CREDENCIALS_USR --password-stdin"
//                    sshScript remote: remote, script: 'login.sh'
//// STOP CONTAINER
//                    writeFile file: 'stop.sh', text: "//!/bin/sh \n docker stop ${env.NameContainer} \n exit 0"
//                    sshScript remote: remote, script: 'stop.sh'
//
//// DELETE CONTAINER
//                    writeFile file: 'delete.sh', text: "//!/bin/sh \n docker rm ${env.NameContainer} \n exit 0"
//                    sshScript remote: remote, script: 'delete.sh'
//
//// DEPLOY CONTAINER
//                    writeFile file: 'deploy.sh', text: "docker run -d --name ${env.NameContainer} -p 3000:3000 $//{env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER}"
//                    sshScript remote: remote, script: 'deploy.sh'
//
//// LOGOUT DOCKERHUB
//                    sshCommand remote: remote, command: "docker logout"
//                    }
//                }
//            }
//        }
//
//        stage('Approval to UAT'){
//            steps{
//                input message: 'Aprueba el deploy a UAT?', submitter: 'reftecnico'
//            }
//        }
//
//        stage('Deploy to UAT'){
//            steps{
//                script{
//                    def remote = [:]
//                    remote.name = 'UAT'
//                    remote.host = "${env.ServerDeploy}"
//                    remote.allowAnyHosts = true
//                    withCredentials([sshUserPrivateKey(credentialsId: 'sshUser-key', keyFileVariable: //'identity', passphraseVariable: 'passphrase', usernameVariable: 'userName')]) {
//                    remote.user = userName
//                    remote.identityFile = identity
//                    remote.passphrase = passphrase
//// LOGIN DOCKERHUB
//                    writeFile file: 'login.sh', text: "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u //$DOCKERHUB_CREDENCIALS_USR --password-stdin"
//                    sshScript remote: remote, script: 'login.sh'
//// STOP CONTAINER
//                    writeFile file: 'stop.sh', text: "//!/bin/sh \n docker stop ${env.NameContainer} \n exit 0"
//                    sshScript remote: remote, script: 'stop.sh'
//
//// DELETE CONTAINER
//                    writeFile file: 'delete.sh', text: "//!/bin/sh \n docker rm ${env.NameContainer} \n exit 0"
//                    sshScript remote: remote, script: 'delete.sh'
//
//// DEPLOY CONTAINER
//                    writeFile file: 'deploy.sh', text: "docker run -d --name ${env.NameContainer} -p 3000:3000 //${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER}"
//                    sshScript remote: remote, script: 'deploy.sh'
//// IMAGE CLEANUP´
//                    sshCommand remote: remote, command: "docker image prune -fa"
//// LOGOUT DOCKERHUB
//                    sshCommand remote: remote, command: "docker logout"
//                    }
//                }
//            }
//        }
//
//    }
//        post{
//            always{
//                sh 'docker logout'
//            }
//        }
//}
