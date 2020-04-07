pipleline{
agent {docker{image 'maven:3.6.3'}}
	stages{
		stage('Build'){
			echo "build"
		}
		stage('Push'){
			sh cho "mvn --version"
		}
		stage('Test'){
			echo "test"
		}

	}
}
