pipeline {
	environment {
		imagename = 'adithyak21/jenkins-docker'
		registryCredential = 'adithya-docckerhub'
		dockerImage = ''
	}
	
	agent any
	
	stages {
		
		stage('Running image') {
			steps{
				script {
				sh 'docker run adithyak21/jenkins-docker:latest'
				}
			}
		}
		stage('Deploy Image') {
			steps{
				script {
				docker.withRegistry( '', registryCredential )
				dockerImage.push('$BUILD_NUMBER')
				dockerImage.push('latest')
				}
			}
		}
	}
}