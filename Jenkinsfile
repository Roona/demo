pipeline{
agent any
	stages{
		stage('Build'){
			echo "build"
		}
		stage('Push'){
			echo "Build"
			echo "$PATH"
			echo "BUILD_NUMBER -$env.BUILD_NUMBER"
			echo "BUILD_ID -$env.BUILD_ID"
			echo "JOB_NAME -$ENV.JOB_NAME"
			
		}
		stage('Test'){
			echo "test"
		}

	}
}
