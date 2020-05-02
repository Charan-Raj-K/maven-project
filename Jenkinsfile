pipeline {
	agent any
	
	stages{
		stage('Build Image'){
			steps{
			   sh 'mvn clean package'
			   sh "docker build . -t tomcatwebapp:${env.BUILD_ID}"
			      }
				}
		
	}
}
