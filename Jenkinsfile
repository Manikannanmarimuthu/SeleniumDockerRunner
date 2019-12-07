pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				bat "docker pull manikannanmarimuthu/sel-docker"
			}
		}
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
	}	
	post{
		always{
		   archiveArtifacts artifacts: 'Output/**'
				bat "docker-compose down"
		}
	}
}