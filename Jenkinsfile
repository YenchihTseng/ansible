pipeline {
    agent any

    stages {
        
        stage('Run Ansible Playbook') {
            steps {
                sshagent(['ansible']) {
                    sh '''
                        ansible-playbook site.yml
                    '''
                }
            }
        }
    }

    post {
        success {
            echo 'Ansible Playbook executed successfully.'
        }
        failure {
            echo 'Ansible Playbook execution failed.'
        }
    }
}

