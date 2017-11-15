pipeline{
   agent any
   stages{
       stage('Build'){
                environment {
      ARTIFACTORY_BUILD_LOGIN = credentials("shivs_creds")
        }
        
          steps{
                 withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD']]){
                    sh 'env'
                    echo "Hello ${env.USERNAME}"
                    echo "Hello ${env.ARTIFACTORY_BUILD_LOGIN}"
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
