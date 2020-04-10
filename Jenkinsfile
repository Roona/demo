pipeline{
	agent {
		kubernetes{
		
		 label 'roona-demo'
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
		
			
			stage('deploy to GKE'){
				steps{
					container('kubectl') {
						   sh """
							 kubectl create deployment kubernetes --image=roona/kubernete:latest
							  kubectl expose deployment kubernetes --type=LoadBalancer --port=8080
							  kubectl get deployments
							   
							"""
					}
				}
			}
			
				

		}
}
