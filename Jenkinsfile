pipeline {
	agent any
	
	stages{
		stage('Build Image'){
			steps{
			   sh 'mvn clean package'
			   sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
			      }
				}
		stage('Push Image'){
            docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            docker.push("${env.BUILD_NUMBER}")
            docker.push("latest")
            } 			
		}
	}
}
