pipeline {
	agent any
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/aishu/extracted/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			sh 'cp target/flipcart.war  /home/aishu/extracted/apache-tomcat-9.0.86/webapps'
			}}
			stage('Docker build'){
		    steps {
			sh 'docker build -t mandharehub/pipelineimage1 .'
			}}
			stage('Container creation'){
		    steps {
			sh 'docker run -it -d --name=container-pipeline mandharehub/pipelineimage1 /bin/bash'
			}}	
}}
