pipeline{
	agent any
	stages{
		stage("Download image"){
			steps{
				bat "docker pull 11239956/selenium-testng-docker:1.0.9"
			}
		}
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
			archiveArtifacts artifacts: "output/**"
			bat "docker-compose down"
		}
	}
}