pipeline {
	agent any
		stages {
			stage('Cloning Git') {
				steps {
					sh 'git clone https://github.com/mdnkrahi/yolov8.git'
				}
			}
			stage('Running image') {
				steps{
					script {
					sh 'mv yolov8/Dockerfile Dockerfile && rm -r yolov8'
					}
				}
			}
			stage('Deploy Image') {
				steps{
					script {
					sh 'docker build -t yolov8 .'
					}
				}
			}
		}
	}
}