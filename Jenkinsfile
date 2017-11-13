pipeline{
   agent any
   stages{
       stage('Build'){
          steps{
                 echo 'hello this is build task'
                 uname -r
                }
       }
       stage('Test'){
          steps{
                 echo 'hello this is test task'
                 uname -a
          }
                }
    }
}
