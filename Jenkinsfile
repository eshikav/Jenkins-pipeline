pipeline{
   agent { label 'Centos' }
   options { 
      timestamps(),
      timeout(time: 30, unit: 'SECONDS')}
   stages{
       stage('Build'){ 

        when {
           expression{ fileExists 'hi.txt' }
        }
          environment {
      ARTIFACTORY_BUILD_LOGIN = credentials("shivs_creds")
      x = readFile 'hi.txt'
      y = pwd tmp: true
             }
        steps{
           dir('shiva'){
                 deleteDir()
                         }
           withCredentials([[$class: 'UsernamePasswordMultiBinding',credentialsId: 'shivs_creds',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD'],[$class: 'FileBinding',credentialsId: 'Jenkins-file',variable: 'JENKINSFILE']]){
                    sh 'env'
                    echo "Hello ${env.USERNAME}"
                    sh "cat ${env.JENKINSFILE}"
                    sh 'uname -r'
                    echo 'this is a polling build'
                    sh 'pwd'
              sleep time:30,unit: 'SECONDS'
              readFile 'hi.txt'
              echo "${env.x}"
              echo "${env.y}"
              stash name: "hi",allowEmpty: false,includes: "*.txt"
                          }
        }
       }
      stage('Deployment'){
         steps{
            dir('ansible'){
               ansiblePlaybook playbook: "sample.yml",inventory: "hosts",colorized: true,tags: "hi"
            }
         }
      }
  
           stage('Test'){
              steps{
              dir('shiva'){
                 unstash  name: 'hi'
              }
              }
              
       
    }
}
}
