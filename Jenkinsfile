pipeline {
    agent { 
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        } 
    }
    stages {
        stage('Build') {
            agent {label 'test'}
            steps {
                sh 'mvn -B -DskipTests clean package'
                sh 'echo c | sudo -S chef-client'
            }
        }
        stage('Test') {
            agent {label 'test'}
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') { 
            agent {label 'test'}
            steps {
                sh './jenkins/scripts/deliver.sh' 
            }
        }
    }
}

