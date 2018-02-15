pipeline{
agent { label 'Centos' }
stages{
  stage('Build'){ 
     steps{
        echo "This is a build stage"
        sh 'uname -r'
        sleep time:30,unit: 'SECONDS'
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
        echo "This is a testing stage"
     }
  }
}
}
