pipeline{
   agent Agent Agent-1
   stages{
       stage('Build'){
                environment {
      ARTIFACTORY_BUILD_LOGIN = credentials("shivs_creds")
        }
        
          steps{
                 withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD'],[$class: 'FileBinding',credentialsId: 'Jenkins-file',variable: 'JENKINSFILE']]){
                    sh 'env'
                    echo "Hello ${env.USERNAME}"
                    sh "cat ${env.JENKINSFILE}"
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
