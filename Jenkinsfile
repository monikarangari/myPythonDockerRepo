
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
steps{sh 'docker build -t demo-repository .' }
}

}
}
