pipeline {
    agent any
  tools {
    maven 'maven3'
	}
	stages{
	    stage('Build') {
		  steps{
		      sh 'mvn clean package'
      }
	  }
	  stage('deploy to prod'){
          steps{
		  sshagent(['tomcat']) {
            sh "scp -o StrictHostKeyChecking=no proddeploy/target/WebApp.war azureuser@20.120.6.254:/opt/tomcat/webapps"
}
		  
	  }
	  }
	  }
	  }
