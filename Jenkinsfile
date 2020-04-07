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
				bat "mvn compile com.google.cloud.tools:jib-maven-plugin:2.1.0:dockerBuild -Dimage=roona/demo"
				echo "build"
			}
		}
		stage('Push'){
			steps{
					bat "mvn --version"
					echo "Build"
					echo "PATH -$env.PATH"
					echo "BUILD_NUMBER -$env.BUILD_NUMBER"
					echo "BUILD_ID -$env.BUILD_ID"
					echo "JOB_NAME -$env.JOB_NAME"
				}
			
		}
		stage('compile com.google.cloud.tools:jib-maven-plugin:2.1.0:dockerBuild'){
			steps{
					bat "mvn clean compile"
			
					echo "test"
			}
		}

	}
}
