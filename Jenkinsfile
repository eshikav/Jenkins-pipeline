pipeline{
   agent any
   stages{
       stage('Build'){
          steps{
                 echo 'hello this is build task'
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
