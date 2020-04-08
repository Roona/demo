pipeline{
	agent any
	environment{
			dockerHome=tool 'myDocker'
			mavenHome=tool 'M3'
			PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
			PROJECT_ID = 'RPSITA'
			CLUSTER_NAME = 'cluster-1'
			LOCATION = 'us-central1-c'
			CREDENTIALS_ID = 'RPSITA'
		}
		stages{
		
			stage('Package'){
				steps{
						bat "mvn clean install"
				
						echo "test"
				}
			}
			
			stage('Package'){
				steps{
						 step([
								$class: 'KubernetesEngineBuilder',
								projectId: env.PROJECT_ID,
								clusterName: env.CLUSTER_NAME,
								location: env.LOCATION,
								manifestPattern: 'deployment.yaml',
								credentialsId: env.CREDENTIALS_ID,
								verifyDeployments: true])
				}
			}
				

		}
}
