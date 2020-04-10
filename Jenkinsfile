pipeline{
	agent {
		kubernetes{
		
		 label 'sample-app'
      defaultContainer 'jnlp'
      yaml """
apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  # Use service account that can deploy to all namespaces
  serviceAccountName: cd-jenkins
  containers:
  - name: golang
    image: golang:1.10
    command:
    - cat
    tty: true
  - name: gcloud
    image: gcr.io/cloud-builders/gcloud
    command:
    - cat
    tty: true
  - name: kubectl
    image: gcr.io/cloud-builders/kubectl
    command:
    - cat
    tty: true
"""
		
		}
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
					container('kubectl') {
						   sh """
							   kubectl get pods
							"""
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
