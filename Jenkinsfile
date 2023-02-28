pipeline {
	agent any
	tools {
		maven "maven3"
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
		}


		stage('unit test'){
			steps{
				sh 'mvn test'
			}
		}
	}
}
