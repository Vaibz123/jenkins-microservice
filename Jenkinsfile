pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3' } }
	environment{
		dockerHome= tool 'myDocker'
		mavenHome= tool 'myMaven'
		PATH= '$dockerHome/bin:$mavenHome/bin:$PATH'
	}
	stages{
		stage('Build') {
			steps{
				sh "mvn --version"
				sh "docker version"
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
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps{
				echo "Integration test"
				sh "mvn test"
			}
		}
	}
	post{
		always{
			echo 'I will always run'
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
