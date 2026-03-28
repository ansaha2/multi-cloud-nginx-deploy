pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/ansaha2/multi-cloud-nginx-deploy.git'
            }
        }

        stage('Deploy using Ansible') {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }

        stage('Restart Nginx') {
            steps {
                sh 'sudo systemctl restart nginx'
            }
        }

    }
}
