pipeline {
    agent { 
        label 'docker-slave'
    }
    stages {
        stage('Build') {
            steps {
                sh 'sshpass -p c ssh -tt test@10.71.71.168'
            }
        }
        
    }
}

