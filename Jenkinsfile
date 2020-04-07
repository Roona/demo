pipeline{
agent any
environment{
		dockerHome=tool 'myDocker'
		mavenHome=tool 'M3'
		PATH="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh "mvn test"
				echo "build"
			}
		}
		stage('Push'){
			steps{
					sh "mvn --version"
					echo "Build"
					echo "PATH -$env.PATH"
					echo "BUILD_NUMBER -$env.BUILD_NUMBER"
					echo "BUILD_ID -$env.BUILD_ID"
					echo "JOB_NAME -$env.JOB_NAME"
				}
			
		}
		stage('Test'){
			steps{
					sh "mvn clean compile"
			
					echo "test"
			}
		}

	}
}
