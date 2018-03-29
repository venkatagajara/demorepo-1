pipeline {
	    agent any 
	       //tools {
	              //maven 'Maven-3.5.3'
	       //}
	    stages {
	       
	           
	        stage('compile') { 
	            steps {
	                  
	                 
	                  withMaven(maven : 'Maven-3.5.3') {
	                  
	                  bat 'mvn compile' //-Dproject.version=${project.version}'
	                  }
	            }
	        }
	        stage('Test') { 
	            steps {
	               bat 'mvn test' // -Dproject.version=${project.version}'
	            }
	        }
	        stage('package') { 
	            steps {
	               bat 'mvn package' // -Dproject.version=${project.version}' 
	            }
	        }
		    
		     stage('Deploy') { 
	            steps {
	               bat 'mvn deploy' // -Dproject.version=${project.version}' 
	            }
	        }
		    
		     stage('sonar') { 
	            steps {
	               bat 'mvn sonar:sonar' // -Dproject.version=${project.version}' 
	            }
	        }
		    
		    
		    
		   
		    
	    }
	}

