pipeline {
	agent none
	environment {
 		 buildid = "envworking"
	}

	tools {
		maven "maven3"
	}

	stages{
		stage('Fetch code') {
			agent {label 'cproject'}
			steps{
				git branch: 'master', url: 'https://github.com/GauthamBappalige/hello-world-war.git'
			}
		}
		stage('Build') {
			agent {label 'cproject'}
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
			agent {label 'jproject'}
			steps{
				echo "testing $buildid"
				sh 'sleep 10'
			}
		}
	}
}
