pipeline {
    agent {
        any {
            image 'node:16.10.0' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'node --version'
                sh 'npm install' 
            }
        }
    }
}