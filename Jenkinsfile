pipeline {
    agent { 
        label 'docker-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'ssh-keyscan -t ecdsa -H >> /home/jenkins/.ssh/known_hosts'
                sh 'sshpass -p c ssh -tt test@10.71.71.168'
            }
        }
        
    }
}

