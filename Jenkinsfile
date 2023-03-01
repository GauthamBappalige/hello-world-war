pipeline {
	agent none
	parameters {
  		string defaultValue: 'master', name: 'branch', trim: true
	}
	environment {
 		 branchname = $branch
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
				echo "testing $branchname"
				sh 'sleep 10'
			}
		}
	}
}
