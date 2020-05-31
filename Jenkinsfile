
//Declarative pipeline

pipeline {
	agent any
    //	agent { docker { image 'maven:3.6.3' } }
	stages {
		stage('Build') {
			steps {
				echo "Build"
				echo "Path -$PATH"
				echo "BuildNumber - $env.BUILD_NUMBER"
				echo "BuildId - $env.BUILD_ID"
				echo "JobName - $env.JOB_NAME"
				echo "BuildTag - $env.BUILD_TAG"
				echo "BuildUrl - $env.BUILD_URL"
			}
		}
		stage('Test') {
			steps {
				echo 'Test'
			}
		}
		stage('Integration Test') {
			steps {
				echo 'Integration Test'
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