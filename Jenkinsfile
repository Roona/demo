pipeline{
agent any
	stages{
		stage('Build'){
			steps{
		
				echo "build"
			}
		}
		stage('Push'){
			steps{
					echo "Build"
					echo "$PATH"
					echo "BUILD_NUMBER -$env.BUILD_NUMBER"
					echo "BUILD_ID -$env.BUILD_ID"
					echo "JOB_NAME -$ENV.JOB_NAME"
				}
			
		}
		stage('Test'){
			steps{
			
			
					echo "test"
			}
		}

	}
}
