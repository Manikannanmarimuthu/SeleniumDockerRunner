pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module book-ticket-module"
			}
		}
	post{
		always{
		   archiveArtifacts artifacts: 'D:/Docker/Workspace/TestRunner/Output/**'
				bat "docker-compose down"
			}
		}
	}
}