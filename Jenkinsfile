pipeline{
   agent { label 'Centos' }
   stages{
       stage('Build'){ 

        when {
           expression{ fileExists 'hi.txt' }
        }
          environment {
      ARTIFACTORY_BUILD_LOGIN = credentials("shivs_creds")
      x = readFile('hi.txt')
      y = pwd tmp: 'true'
             }
        steps{
           dir('shiva'){
                 deleteDir()
                         }
           dir('shiva'){withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD'],[$class: 'FileBinding',credentialsId: 'Jenkins-file',variable: 'JENKINSFILE']]){
                    sh 'env'
                    echo "Hello ${env.USERNAME}"
                    sh "cat ${env.JENKINSFILE}"
                    sh 'uname -r'
                    echo 'this is a polling build'
                    sh 'pwd'

              echo "${env.x}"
                                     }
                       }
          }
       }
    }
}
