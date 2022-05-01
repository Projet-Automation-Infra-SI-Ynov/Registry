node {
    stage('Git checkout') {
        git branch: "${params.BRANCH}", url: 'https://github.com/Projet-Automation-Infra-SI-Ynov/Registry'
    }
    stage('Add Registry address IP in ansible role') {
        sh "sed -i 's/REGISTRY2/${params.REGISTRY_IP}/g' ./ansible/Registry/tasks/main.yml"
    }
    stage('Add Registry address IP in inventory file') {
        sh "sed -i 's/IP_REGISTRY/${params.REGISTRY_IP}/g' ./ansible/registry.ini"
    }
    stage('Add Registry address IP in docker-compose file') {
        sh "sed -i 's/IP_REGISTRY/${params.REGISTRY_IP}/g' ./docker-compose.yml"
    }
    stage('Execute playbook') {
        sh "ansible-playbook -i ./ansible/registry.ini ./ansible/registry.yml"
    }
}