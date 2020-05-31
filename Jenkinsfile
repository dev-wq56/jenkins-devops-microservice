
//Declarative pipeline

pipeline {
	agent none
	stages {
		stage('Build') {
			agent { docker { image 'maven:3.6.3' } }
			steps {
				sh 'mvn --version'
				echo 'Build'
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