pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }

	stages{
		stage('Build') {
			steps{
				//sh "mvn --version"
				echo "Build"
				echo "Build no. - $env.BUILD_NUMBER"
				echo "Build id - $env.BUILD_ID"
				echo "Build tag - $env.BUILD_TAG"
				echo "Build url - $env.BUILD_URL"
				echo "Path: $PATH"
				echo "Job_name: $env.JOB_NAME "
			}
		}
		stage('Test') {
			steps{
				echo "Test"
			}
		}
	}
	post{
		always{
			echo 'I will allways run'
		}
		failure{
			echo 'I run when you fail'
		}
		success{
			echo 'I run when you go green'
		}
		changed{
			echo 'I run if there is change from fail to pass and viceversa'
		}
	}
}
