pipeline {
    agent {
        any {
            image 'node:16.10.0' 
            args '-p 3000:3000' 
        }
    }

    environment {
        CI = 'true'
    }   
    stages {
        stage('Build') { 
            steps {
                sh 'node --version'
                sh 'npm install' 
            }
        }
    
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}