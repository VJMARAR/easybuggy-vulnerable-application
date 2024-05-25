pipeline {
  agent any
  tools { 
        maven 'Maven_3_9_6'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asgbuggywebapp -Dsonar.organization=asgbuggywebapp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=1f89e388b4a34148aeab89c922f191253a368878'
			}
        } 
  }
}
