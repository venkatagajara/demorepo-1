pipeline {
	    agent any 
	       //tools {
	              //maven 'Maven-3.5.3'
	       //}
	
	  parameters {
        string(defaultValue: '', description: '', name: 'version')
		  
    }
	    stages {
	       
	           
	        stage('compile') { 
	            steps {
	                  
	                 
	                  withMaven(maven : 'Maven-3.5.3') {
	                          echo "${params.version}"
				  bat 'mvn compile -Dversion="${params.version}"' 
				  
	                  }
	            }
	        }
	        stage('Test') { 
	            steps {
	               bat 'mvn test' 
	            }
	        }
	        stage('package') { 
	            steps {
	               bat 'mvn package -Dmaven.test.skip=true -Dversion="${params.version}"'
	            }
	        }
		     stage('sonar') { 
	            steps {
	               bat 'mvn sonar:sonar -Dmaven.test.skip=true'
	            }
	        }
		    
		    
		     stage('Deploy') { 
	            steps {
	               bat 'mvn deploy -Dmaven.test.skip=true' 
	            }
	        }
		    
		    		    
		    
		   
		    
	    }
	}

