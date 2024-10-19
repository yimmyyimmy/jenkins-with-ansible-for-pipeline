pipeline {
  agent { 
  label 'ansible'
  }
  
  environment {
   AWS_EC2_PRIVATE_KEY=credentials('ec2-private-key') 
  }
  
  stages {
    
    //Get the Code from GitHub Repo
    stage('SCM'){
      steps{
        //git branch: 'master', credentialsId: 'aeeaa4ad-45b4-4c30-9401-586ac501a9bb', url: 'https://github.com/MithunTechnologiesDevOps/jenkins-with-ansible.git'
        git branch: 'master', credentialsId: 'git_credentials', url: 'https://github.com/yimmyyimmy/jenkins-with-ansible-for-pipeline.git'
      }
    }
     
    //Run the playbook
    stage('RunPlaybook') {
      steps {
        //sh "ansible-playbook -i inventory/canarabank.hosts --private-key=$AWS_EC2_PRIVATE_KEY /etc/ansible/playbooks/tomcatinstallaion.yml --ssh-common-args='-o StrictHostKeyChecking=no'"
        sh "ansible-playbook /etc/ansible/tomcatinstallaion.yml"
      }
    }
  
  }//stages closing
}//pipeline closing
