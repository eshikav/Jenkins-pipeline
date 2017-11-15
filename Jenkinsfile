pipeline{
   agent any
   stages{
       stage('Build'){
          withCredentials([UsernamePasswordMultiBinding(credentialsId: shivs_creds,usernameVariable: USERNAME,passwordVariable: PASSWORD)])
          steps{
                 echo $env.USERNAME
                 sh 'uname -r'
                 echo 'this is a polling build'
                }
       }
       stage('Test'){
          steps{
                 echo 'hello this is test task'
                 sh 'uname -a'
                 sh 'pwd'
                 sh 'sleep 10'
          }
                }
    }
}
