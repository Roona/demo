pipeline{
agent any
environment{
		dockerHome=tool 'myDocker'
		mavenHome=tool 'M3'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
	
		stage('Package'){
			steps{
					bat "mvn clean install"
			
					echo "test"
			}
		}
		stage('Build Docker Image'){
			steps{
				script{
				dockerImage=docker.build("roona/demo:${env.BUILD_TAG}")
				}
				
			}
		}
		stage('Push Docker Image'){
			steps{
					script{
							docker.withRegistry('','dockehub'){
							dockerImage.push();
							dockerImage.push('latest');
							}
					}
				}
			}
		
		

	}
}
