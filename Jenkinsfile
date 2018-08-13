pipeline {
	    agent any 
	       //tools {
	              //maven 'Maven-3.5.3'
	       //}
	
	//  parameters {
       // string(defaultValue: '', description: '', name: 'version')
		  
  //  }
	    stages {
	       
	           
	        stage('build') { 
	            steps {
	                  
	                  withAnt(installation: 'Ant-1.9.12', jdk: 'JAVA_HOME') {
	                         // echo "${params.version}"
				 // sh 'mvn compile -Dparams.version="${params.version}"'
				 // sh 'mvn compile'
				  bat 'ant build'
				  
	                  }
	            }
	        }
	    }
	}
