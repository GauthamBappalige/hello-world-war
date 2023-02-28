pipeline {
	agent any
	tools {
		maven "maven3"
	}
	stages{
		stage('Build') {
			steps{
				sh 'mvn install'
			}
		}
		stage('deploy') {
			steps{
				sh 'mvn deploy'
			}
		}
		stage('test') {
			steps{
				sh 'mvn test'
			}
		}	
	}
}
