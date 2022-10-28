 node{
      stage('Clone') {
          checkout scm
      }
      stage('Ansible') {
          ansiblePlaybook (
            inventory: 'inventaire',
            playbook: 'playbook.yml',
            colorized: true,
        )
      }
}
