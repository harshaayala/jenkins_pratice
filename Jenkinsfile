pipeline{
	agent any
	stages{
		stage('Build'){
			steps{
				sh "mvn --version"
				echo "BUILD-NUMBER -$env.BUILD_NUMBER"
				echo "$env.JOB_NAME"
				echo "Build"
				echo "Test"
			}
		post{
			always{
				echo "success"
			}
			success{
				echo "build sucess"
			}
			failure{
				echo "failed"
			}
		}
		}
	}
}
