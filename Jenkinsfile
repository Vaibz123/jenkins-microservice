pipeline {
	//agent any
	agent {docker {image 'maven:3.6.3' }}

	stages{
		stage('Build') {
			steps{
				sh "mvn --version"
				echo "Build"
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
