pipeline {
    agent { 
        label 'docker-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'apt-get update'
                sh 'apt-get install sshpass'
                sh "ssh-keygen -t rsa -P '' -f /root/.ssh/id_rsa"                         
                sh 'ssh-keyscan -t ecdsa -H >> /root/.ssh/known_hosts'
                sh 'sshpass -p c ssh -tt test@10.71.71.168'
            }
        }
        
    }
}

