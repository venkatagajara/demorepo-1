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
	               bat 'mvn package -Dmaven.test.skip=true'
	            }
	        }
		     stage('sonar') { 
	            steps {
	               bat 'mvn sonar:sonar -Dmaven.test.skip=true'
	            }
	        }
		    
		    
		     stage('Deploy') { 
	            steps {
	               bat 'mvn deploy -Dmaven.test.skip=true' // -Dproject.version=${project.version}' 
	            }
	        }
		    
		    		    
		    
		   
		    
	    }
	}

