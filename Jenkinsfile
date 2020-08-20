pipeline{
		agent any
		stages{
			stage('Clone repo'){
				steps{
					def exists = fileExists './chaperootodo_client'
					if (exists) {
						println "File already exists"
					} else {
						sh "git clone https://gitlab.com/qacdevops/chaperootodo_client.git"
					}
				}
			}
			stage('Install Docker and Docker-Compose'){
				steps{
					sh '''
					curl https://get.docker.com | sudo bash
					sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
					sudo chmod +x /usr/local/bin/docker-compose
					'''
				}
			}
		   stage('Deploy the application'){
				steps{
					sh "sudo docker-compose up -d"
				}
			}
		}// end stages
}// end pipeline
