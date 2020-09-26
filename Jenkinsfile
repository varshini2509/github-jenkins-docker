pipeline {
	environment {
		registry = "chakilams3/github-jenkins-docker"
		registryCredential = 'dockerhub'
		dockerImage = ''
	}
	agent any
	stages {
		stage("Building docker image") { 
			steps {
				script {
					dockerImage = docker.build registry + ":$BUILD_NUMBER"
				}
			}
		}
		stage("Pushing image to DockerHub") { 
			steps {
				script {
					docker.withRegistry( '', registryCredential ) {
						dockerImage.push()
						dockerImage.push( 'latest' )
					}
				}
			}
		}
		stage("Testing") {
			steps {
				echo "This is testing the Testing stage"

			}
		}
	}
}