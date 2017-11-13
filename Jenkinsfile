pipeline{
   agent any
   stages{
       stage('Build'){
          steps{
                 echo 'hello this is build task'
                 sh uname -r
                }
       }
       stage('Test'){
          steps{
                 echo 'hello this is test task'
                 sh uname -a
          }
                }
    }
}
