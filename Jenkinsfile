pipeline {
    agent none
    stages {
        stage('deploy with ansible') {
            agent { docker { image 'registry.gitlab.com/robconnolly/docker-ansible:latest' } }
            steps {
                script {
                    sh '''
                        cd ansible
                        ansible-playbook -i prod.yml alpinehelloworld.yml
                      '''
                }
            }
        }
    }
}
