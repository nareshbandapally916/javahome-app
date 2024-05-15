pipeline {
    agent any
    stages {
        stage('SCM Checkout') {
            steps {
                git branch: 'develop', url: 'https://github.com/nareshbandapally916/javahome-app'
            }
        }
        stage('Execute Ansible') {
            steps {
                ansiblePlaybook credentialsId: 'private-key', 
                                disableHostKeyChecking: true, 
                                installation: 'ansible2', 
                                inventory: 'dev.inv', 
                                playbook: 'apache.yml', 
                                vaultTmpPath: ''
            }
        
        }
    
    }
}
