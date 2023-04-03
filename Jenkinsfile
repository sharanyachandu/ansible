pipeline {
    agent { label 'ws' }
    environment { 
        SSH_CREDENTIALS = credentials('SSH_CRED') 
    }    
    stages {
        stage('Performing Ansible Dry Run') {
            steps {
                sh "env"
                sh "ansible-playbook robot-dryrun.yaml -e COMPONENT=mongodb -e ansible_user=${SSH_CREDENTIALS_USE} -e ansible_password=${SSH_CREDENTIALS_PSW} -e ENV=qa"
            }
        }
    }
}