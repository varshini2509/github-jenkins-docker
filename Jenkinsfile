pipeline {
	environment {
		registry = "chakilams3/github-jenkins-docker"
		registryCredential = 'dockerhub'
		dockerImage = ''
		dockerRunCommand = 'docker run -d -p 8080:8080 -name myapp chakilams3/github-jenkins-docker'
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
		stage("Wait time") {
			steps {
				sleep(5)
			}
		}
		stage("Deployment to Dev environment") {
			steps {
				sshagent(['dockerdeploy']) {
	            sh 'ssh -o StrictHostKeyChecking=no dockerdeploy@13.233.254.50 ${dockerRunCommand}'
				}	 
			}
		}

	}
}