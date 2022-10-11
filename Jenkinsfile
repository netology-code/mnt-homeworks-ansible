pipeline {
    agent {
        label "linux"
    }
    stages {
        stage('Checkout repo'){
            steps {
                dir('freestyle') {
                git branch: 'main', credentialsId: 'e8159eed-9d1a-43ac-a5e3-a415afe999a0', url: 'git@github.com:netology-code/mnt-homeworks-ansible.git'
                }
            }
        }
        stage ('Prepare for molecule'){
            steps {
                sh 'pip3 install --force "molecule==3.3.4" "molecule_docker==0.3.3" yamllint ansible-lint'
            }
        }
        stage('Run Molecule'){
            steps {
                dir('freestyle'){
                    sh 'molecule test'
                }
            }
        }
    }
}