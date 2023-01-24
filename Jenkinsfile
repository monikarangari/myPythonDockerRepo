
pipeline
{
agent any 
  environment{
  registry="652912600783.dkr.ecr.us-east-1.amazonaws.com/demo-repository"
  }
stages{
stage('scm checkout'){
steps{checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/monikarangari/myPythonDockerRepo']]])}
}
  
  stage('code build'){
steps {withMaven(globalMavenSettingsConfig: '3f8bb0dc-be09-46c7-9930-a5bf27ce791a', jdk: 'LocalJDK', maven: 'LocalMaven', mavenSettingsConfig: '88ab8890-4885-4ddd-8d16-3c1b233b3d8f') 
{sh 'mvn clean package'}
}
}  
stage('docker image')
{
steps{sh 'docker build -t demo-repository .' }
}
stage('list-docker image')
{
steps{sh 'docker images' 
sh 'docker ps'}
}


}
}
