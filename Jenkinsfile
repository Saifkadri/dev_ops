pipeline {
      agent any
          stages {

	        stage('Checkout GIT ') {
                 steps {
                    echo 'Pulliing ...';
			 git branch: 'Youssef', credentialsId: 'Git', url: 'https://github.com/Saifkadri/dev_ops.git'
		           
                        }
			}
		 stage('Cleaning the project') {
                 steps{
                    sh "mvn -B -DskipTests clean  "
                    }
	         
                 
}
		   stage('Build') {
      		    steps {
        		sh 'mvn -B -DskipTests clean package'
      		          }
            	}
		  

		  
		   /* stage('Testing maven') {
		        steps {
		        sh """mvn -version
		              mvn clean package """
	                   }
	            }
		    */

		  stage('SonarQube analysis') {
		        steps {
		        withSonarQubeEnv(installationName: 'Sonar') {
		        sh 'mvn clean clean -DskipTests package sonar:sonar'
	                  }
	                }
	            }
		  
		    stage("NEXUS") {
        	    steps {
		        sh 'mvn clean deploy -DskipTests'
                      }
                }
}
}
