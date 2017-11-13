pipeline{
   agent any
   stages{
       stage('Build'){
          steps{
                 echo 'hello this is build task'
                 echo `uname -r`
                }
       }
       stage('Test'){
          steps{
                 echo 'hello this is test task'
                 echo `uname -a`
          }
                }
    }
}
