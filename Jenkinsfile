
pipeline
{
agent any 
stages{
stage('scm checkout'){
steps{checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/monikarangari/myPythonDockerRepo']]])}
}
}
}
