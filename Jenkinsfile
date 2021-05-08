pipeline
{

agent any
	stages
	{
	
		stage ('scm checkout')
		{
			steps {
				git branch: 'master', url: 'https://github.com/ankitasharma-1/maven-project.git'
		  		  }
		}
	
		stage ('compile src code')
		{
 			 steps {
 	 			withMaven(jdk: 'Local_JDK', maven: 'LocalMvn') 
 	 			   	{
     			sh 'mvn compile'
					}
       			       }

	         }
		
		stage ('testing src code')
		{
 			 steps {
 	 			withMaven(jdk: 'Local_JDK', maven: 'LocalMvn') 
 	 			   	{
     			sh 'mvn test'
					}
       			       }

	         }
		
		stage ('building')
		{
 			 steps {
 	 			withMaven(jdk: 'Local_JDK', maven: 'LocalMvn') 
 	 			   	{
     			sh 'mvn package'
					}
       			       }

	         }
		
		 stage ("tomcat dev deployment")
     {
      steps{
         sshagent(['Tomcat_Key']) {
          sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.32.209:/var/lib/tomcat/webapps'
	
	}
}
