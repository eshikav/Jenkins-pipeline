pipeline{
   agent any
   stages{
       stage('Build'){
          
          steps{
                 withCredentials(UsernamePasswordMultiBinding(credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD')){
                 echo $USERNAME
                 sh 'uname -r'
                 echo 'this is a polling build'
                }
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
