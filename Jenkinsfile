pipeline
{

agent any
stages
{
	
	stage ('scm checkout')
	{
	steps {
		git 'https://github.com/ankitasharma-1/maven-project.git'
		  }
	}
	
	stage ('compile src code')
	{
 	 steps {
 	 	withMaven(jdk: 'local_JDK', maven: 'local_Maven') {
    'mvn compile'
		}
 	 	}
 	 }

 	 stage ('testing')
 	 {
 	 steps {
 	 withMaven(jdk: 'local_JDK', maven: 'local_Maven') {
    'mvn test'
		}
 	 	}
 	 }
}

}
