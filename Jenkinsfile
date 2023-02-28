pipeline {
	agent any
	tools {
	maven "maven3"
	}
	stages {
		stage('Fetch code') {
			steps {
				git branch: 'master', url: 'https://github.com/GauthamBappalige/hello-world-war.git'
			}
		}

		stage('Build'){
			steps{
				sh 'mvn install -Dskiptests'
			}
			post {
				sucess {
					echo 'now archiving it ..'
					archiveArtifacts artifacts: '**/target/*.war'

				}
			}
			stage('unit test'){
			steps{
				sh 'mvn test'
			}
		}
	}
}
