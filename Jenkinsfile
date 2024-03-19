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
			sh 'docker build -t mandharehub/piplineimage1 .'
			}}
			stage('Container creation'){
		    steps {
			sh 'docker run -it -d --name=pipeline1 mandharehub/piplineimage1 /bin/bash'
			}}	
}}
