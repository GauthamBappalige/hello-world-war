pipeline {
	agent {label 'cproject'}
	tools {
		maven "maven3"
	}

	stages{
		stage('Fetch code') {
			steps{
				git branch: 'master', url: 'https://github.com/GauthamBappalige/hello-world-war.git'
			}
		}
		stage('Build') {
			steps{
				sh 'mvn install'
			}
			post {
	           success {
	              echo 'Now Archiving it...'
	              archiveArtifacts artifacts: '**/target/*.war'
	           }
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
