pipeline {
    agent {
  label 'linux'
    }
    stages {
        stage('First') {
            steps {
                sh 'ansible-playbook --version'
            }
        }
        stage('Second') {
            steps {
                sh 'echo Hello'
                sh ' echo "second step"'
            }
        }
    }
}
