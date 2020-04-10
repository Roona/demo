pipeline{
	agent ANY
	environment{
			
			PROJECT_ID = 'RPSITA'
			CLUSTER_NAME = 'cluster-1'
			LOCATION = 'us-central1-c'
			CREDENTIALS_ID = 'RPSITA'
		}
		stages{
		
			
			
			stage('deploy to GKE'){
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
