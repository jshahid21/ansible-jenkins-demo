pipeline {

  agent any

  environment {
    SVC_ACCOUNT_KEY = credentials('terraform-auth-js')
  }

  stages {

    stage('Ansible Playbook') {
      steps {
          sh 'sudo ansible-playbook -i /var/lib/jenkins/workspace/tajJS/ansible-playbook/hosts --private-key=/var/lib/jenkins/.ocijs/id_rsa /var/lib/jenkins/workspace/tajJS/ansible-playbook/main.yml'
      }
    }
  }
}
