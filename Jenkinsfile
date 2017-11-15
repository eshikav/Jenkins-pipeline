pipeline{
   agent any
   stages{
       stage('Build'){
          
          steps{
                 withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD']]){
                    sh 'env'
                    sh '${USERNAME}'
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
