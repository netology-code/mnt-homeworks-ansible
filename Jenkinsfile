pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('mnt-homeworks-ansible') {
                    git branch: 'main', credentialsId: '2ae3ac29-908a-45f9-9cea-90d9ab9db609', url: 'git@github.com:netology-code/mnt-homeworks-ansible.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'molecule test'
                }
            }
        }
    }
}