pipeline {
	agent any
	stages {
		stage('Clone repo') {
			steps{
				sh "./scripts/clone-repo.sh"
			}
		}
	    stage('Install Docker and Docker-Compose') {
			steps {
				sh "./scripts/install-docker.sh"
				}
			}
	    stage('Deploy the application') {
			steps {
				sh "./scripts/deploy-app.sh"
			}
	    }
	}// end stages
}// end pipeline
