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
                sh 'ssh-keyscan -t ecdsa -H 10.71.71.168 >> /root/.ssh/known_hosts'
                sh 'sshpass -p root ssh root@10.71.71.168'
                sh 'chef-client'
            }
        }
        
    }
}

