pipeline {
	environment {
		imagename = 'adithyak21/jenkins-docker'
		registryCredential = 'adithya-docckerhub'
		dockerImage = ''
	}
	
	agent any
	
	stages {
		stage('Cloning Git') {
			steps {
				git([url: 'https://github.com/adithyak21/simple-docker.git', branch: 'main'])
			}
		}
		stage('Building image') {
			steps{
				script {
				dockerImage = docker.build imagename
				}
			}
		}
		stage('Running image') {
			steps{
				script {
				sh 'docker run ${imagename}:latest'
				}
			}
		}
		stage('Deploy Image') {
			steps{
				script {
				docker.withRegistry( '', registryCredential ) {
				dockerImage.push('$BUILD_NUMBER')
				dockerImage.push('latest')
				}
			}
		}
	}
}