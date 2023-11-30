pipeline {
	agent any
		stages {
			stage(‘Cloning Git’) {
				steps {
					git([url: ‘https://github.com/mdnkrahi/test.git', branch: ‘main’])
				}
			}
			stage(‘Running image’) {
				steps{
					script {
					sh “mv yolov8/Dockerfile Dockerfile && rm -r yolov8”
					}
				}
			}
			stage(‘Deploy Image’) {
				steps{
					script {
					sh “docker build -t yolov8 .”
					}
				}
			}
		}
	}
}