pipeline{
   agent any
   stages{
       stage('Build'){
          steps{
                 sh echo 'hello this is build task'
                 sh echo `uname -r`
                }
       }
       stage('Test'){
          steps{
                 sh echo 'hello this is test task'
                 sh echo `uname -a`
          }
                }
    }
}
