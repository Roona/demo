pipeline{
	agent {
		kubernetes{}
	}
	environment{
			
			PROJECT_ID = 'RPSITA'
			CLUSTER_NAME = 'jenkins-cd'
			LOCATION = 'us-east1-d'
			CREDENTIALS_ID = 'RPSITA'
		}
		stages{
		
			
			stage('test'){
				steps{
					container('jnlp') {
						  sh("kubectl get pods")
					}
				}
			}
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
