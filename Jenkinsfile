pipeline{
	agent any
	stages{
		stage('Package'){
			steps{
				sh "mvn Package -DskipTests"
			}
		}
		stage('Build Docker image'){
			steps{
				script{
					dockerImage=docker.build("hash48/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		
		}
		stage('Push Docker Image'){
			steps{
				script{
					docker.withRegistry("",'dockerhub')
					dockerImage.push()
					dockerImage.push('latest')
				}
			}
		}
		}
	}
