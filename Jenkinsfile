pipeline {
 environment {
 registry = “chakilams3/simple-nginx:v41”
 registryCredential = ‘dockerhub’
 dockerImage = ‘’
 }
 agent any
 stages {
 stage(‘Cloning Git’) {
 steps {
 git ‘ssh://git@18.139.110.189:2222/git-server/repos/webapp.git’
 }
 }
 stage(‘Building Docker Image’) {
 steps{
 script {
 dockerImage = docker.build registry + “:$BUILD_NUMBER”
 }
 }
 }
 stage(‘Push Image to Docker Hub ‘) {
 steps{
 script {
 docker.withRegistry( ‘’, registryCredential ) {
 dockerImage.push()
 dockerImage.push(‘latest’)
 }}
 }}
 }
}
