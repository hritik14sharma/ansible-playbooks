pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False' // Prevents SSH key checking prompts
    }
    stages {
        stage('Checkout Code') {
            steps {
                // This stage checks out the code from your GitHub repository
                git branch: 'main', url: 'https://github.com/hritik14sharma/ansible-playbooks.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                // This stage runs the Ansible playbook
                ansiblePlaybook(
                    playbook: 'playbook.yml', // Specifies the playbook file
                    inventory: 'inventory.ini', // Specifies the inventory file
                    colorized: true // Adds color to the Ansible output in Jenkins
                )
            }
        }
    }
}
