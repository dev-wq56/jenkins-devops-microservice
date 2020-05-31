
//Declarative pipeline

pipeline {
	agent any
    //	agent { docker { image 'maven:3.6.3' } }
	environment{

		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH  = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "Path -$PATH"
				echo "BuildNumber - $env.BUILD_NUMBER"
				echo "BuildId - $env.BUILD_ID"
				echo "JobName - $env.JOB_NAME"
				echo "BuildTag - $env.BUILD_TAG"
				echo "BuildUrl - $env.BUILD_URL"
			}
		}
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('Integration Test') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	}
	post {
		always {
			echo 'I run always'
		}
		success {
			echo 'I run when successful'
		}
		failure {
			echo 'I run when you fail'
		}
	}
}