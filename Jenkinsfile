pipeline {    
    agent any    

    stages {    

          stage('Checkout') {
            steps {
                dir('AnsibleDemo') {
                    git branch: 'main', url: 'https://github.com/Urmilaa/Jenkins-Ansible-Integration'
                }
            }
        }

        stage('Execute playbook') {           
            steps {          
                ansiblePlaybook(
                    credentialsId: 'JenkinAnsible',
                    disableHostKeyChecking: false,
                    installation: 'Ansible',
                    inventory: "${WORKSPACE}/AnsibleDemo/Inventory2.yaml",
                    playbook: "${WORKSPACE}/AnsibleDemo/multi_play.yaml",
                    vaultTmpPath: ''
                )
            }
        }    
    }
}
