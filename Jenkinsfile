
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
  
stage('docker image')
{
steps{// This step should not normally be used in your script. Consult the inline help for details.
withDockerRegistry(credentialsId: 'ecr:us-east-1:awsecr', url: 'https://652912600783.dkr.ecr.us-east-1.amazonaws.com/demo-repository')
  {
    sh 'docker build -t 652912600783.dkr.ecr.us-east-1.amazonaws.com/demo-repository:${BUILD_NUMBER} .'
    sh 'docker push 652912600783.dkr.ecr.us-east-1.amazonaws.com/demo-repository:${BUILD_NUMBER}'
}}
}

}
}
