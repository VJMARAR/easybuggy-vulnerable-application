pipeline{
      agent any
      tools{
            maven 'Maven_3_2_5'
      }
      stages{
            stage('SAST scan using SonarCloud'){
                  steps{
                        sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=asbuggyweb -Dsonar.organization=asbuggyweb -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=75659ff20061eb3d1a534a337de5356a4e2933fb'
                  }
            }
            stage('SCA using SNYK'){
                  steps{
                        withCredentials([string(credentialsId: 'SNYK_TOKEN' , variable: 'SNYK_TOKEN')]){
                              sh 'mvn snyk:test -fn'
                        }
                  }
            }
      }
}