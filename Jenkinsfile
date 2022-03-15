pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('Install molecule') {
            steps{
                sh 'cd mnt-homeworks-ansible && pip3 install -r test-requirements.txt'
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                sh 'cd mnt-homeworks-ansible && molecule test'
            }
        }
    }
}