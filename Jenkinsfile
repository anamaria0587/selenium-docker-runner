pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				bat "docker-compose up search-module1 search-module2 --no-color"
			}
		}
		stage("Stop Grid"){
			steps{
				bat "docker-compose down"
			}
		}
	}
}