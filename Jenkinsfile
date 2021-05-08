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

		}}
}
