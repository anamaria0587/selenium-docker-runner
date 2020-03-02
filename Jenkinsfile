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
				bat "docker-compose up search-module1 search-module2"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: '**output/**'
			bat "docker-compose down"
		}
	}
}