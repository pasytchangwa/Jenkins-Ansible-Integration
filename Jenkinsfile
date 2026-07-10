pipeline {    
    agent any    

    stages {    

          stage('Checkout') {
            steps {
                dir('AnsibleDemo') {
                    git branch: 'main', url: 'https://github.com/pasytchangwa/Jenkins-Ansible-Integration'
                }
            }
        }

        stage('Execute playbook') {           
            steps {          
                ansiblePlaybook(
                    credentialsId: 'JenkinsAnsible',
                    disableHostKeyChecking: false,
                    installation: 'Ansible',
                    inventory: "${WORKSPACE}/AnsibleDemo/Inventory.yaml",
                    playbook: "${WORKSPACE}/AnsibleDemo/install_nginx_PB.yml",
                    vaultTmpPath: ''
                )
            }
        }    
    }
}
