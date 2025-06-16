pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Manasi6901/myapp.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }
        stage('Tag & Push to Registry') {
            steps {
                sh 'docker tag myapp:latest 172.31.12.212:5000/myapp:latest'
                sh 'docker push 172.31.12.212:5000/myapp:latest'
            }
        }
        stage('Deploy with Ansible') {
            steps {
                sh 'ansible-playbook -i "${TARGET_HOST}," -u ${DEPLOY_USER} --private-key ~/.ssh/manasi-key.pem deploy.yml'
            }
        }
    }
}
