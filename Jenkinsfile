
//Declarative pipeline
pipeline {
    agent any
// 	agent { docker { image 'node:13.8' } }
//hi
	environment {
	    dockerHome = tool 'myDocker'
	    mavenHome = tool 'myMaven'
	    PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
	    stage('Build') {
	        steps {
// 	            sh 'node --version'
	            sh 'mvn --version'
	            sh 'docker --version'
	            echo "Build"
	            echo "$PATH"
	            echo "BUILD_NUMBER - $env.BUILD_NUMBER"
	            echo "BUILD_ID - $env.BUILD_ID"
	            echo "JOB_NAME - $env.JOB_NAME"
	            echo "BUILD_TAG - $env.BUILD_TAG"
	            echo "BUILD_URL - $env.BUILD_URL"
	        }
        }
	    stage('Test') {
        	 steps {
        	      echo "Test"
        	      }
        }
	    stage('Integration test') {
        	  steps {
        	       echo "Integration Test"
        	       }
              }
	   }
	   post {
	       always {
	            echo 'I am Awesome. I run always'
	       }
	       success {
	            echo 'I run when you are successful'
	       }
	       failure {
	           echo 'I run when you are fail'
	       }
	   }
}
