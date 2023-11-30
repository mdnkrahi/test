pipeline {
	agent any
	
	stages {
		stage('Deploy Image') {
			steps{
				script {
				sh 'apt install docker.io -y'
				}
			}
		}
	}
}