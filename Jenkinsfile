pipeline {
    agent {label 'master'} 
    stages  {
        stage('Clean workspace'){
            steps {
                cleanWs()
            }
        }
		
        stage ('git clone')
   		 {
            steps{
				sh'''
					echo "${WORKSPACE}"
					
					git clone https://github.com/hitechvenkadesh/terrab90.git
					pwd
					ls
				
				'''
            }
        }
    
		stage ('terraform init') {
			steps{
	  
				sh'''
					
					cd /var/lib/jenkins/workspace/terradecpipeline/terrab90/
					
					terraform init
				   
				'''
			} // end of steps
		} //end of stage
		
		stage ('terraform plan') {
			steps{		
	  
				sh'''
					
					cd /var/lib/jenkins/workspace/terradecpipeline/terrab90/
					
					terraform plan
					
				'''
			} // end of steps
		} //end of stage
		
		stage ('terraform apply') {
			steps{
	  
				sh'''
					
					cd /var/lib/jenkins/workspace/terradecpipeline/terrab90/
					
					terraform apply -auto-approve
				   
				'''
			} // end of steps
		} //end of stage
  }
}
