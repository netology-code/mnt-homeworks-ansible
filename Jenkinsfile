pipeline {
    agent {
        label "linux"
    }
    stages {
        stage('Checkout repo'){
            steps {
                dir('freestyle') {
                git branch: 'main', credentialsId: '4d2e8f2e-5af7-4ebe-8ab6-2ea1f1df37da', url: 'git@github.com:netology-code/mnt-homeworks-ansible.git'
                }
            }
        }
        stage ('Prepare for molecule'){
            steps {
                sh 'pip3 install "molecule==3.3.4" "molecule_docker==0.3.3" yamllint ansible-lint'
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