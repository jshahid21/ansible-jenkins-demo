pipeline {

  agent any

  environment {
    SVC_ACCOUNT_KEY = credentials('terraform-auth-js')
  }

  stages {

    stage('Checkout') {
      steps {
        checkout scm
        sh 'echo $SVC_ACCOUNT_KEY | base64 -d > terraform.tfvars'
      }
    }

    stage('Ansible Playbook') {
      steps {
          sh 'sudo ansible-playbook -i /var/lib/jenkins/workspace/tajJS/ansible-playbook/hosts --private-key=/var/lib/jenkins/.ocijs/id_rsa /var/lib/jenkins/workspace/tajJS/ansible-playbook/main.yml'
      }
    }
  }
}
