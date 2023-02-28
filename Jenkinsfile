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
				echo "deploying"
				sh 'sleep 10'
			}
		}
		stage('test') {
			steps{
				echo "testing"
				sh 'sleep 10'
			}
		}	
	}
}
