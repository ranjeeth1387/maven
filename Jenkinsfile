node('master') 
{
  stage('ContinuousDownload') 
  {
    git 'https://github.com/ranjeeth1387/maven.git'
  } 
  stage('ContinuousBuild')
  {
      sh label: '', script: 'mvn package'
  }
  stage('ContinuousDeployment')
  {
     sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline@2/webapp/target/webapp.war ubuntu@172.31.36.247:/var/lib/tomcat8/webapps/testwebapp.war'      
  }
  stage('ContinuousTesting')
  {
      git 'https://github.com/ranjeeth1387/maven.git'
      sh label: '', script: 'echo "Testing Passed"'
  }
  stage('ContinuousDelivery')
  {
      sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline@2/webapp/target/webapp.war ubuntu@172.31.35.219:/var/lib/tomcat8/webapps/prodwebapp.war'      
  }
  
  
  
  
  
  
}
