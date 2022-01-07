pipeline {
    agent {
        docker {
            image 'node:lts-alpine'
            args '-v $HOME/.npm:/root/.npm'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        //CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'node --version'
                sh 'npm --version'
                sh 'id'
                sh 'pwd'
                sh 'npm config list'
                sh 'npm config ls -l'
                sh 'npm cache clean --force'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}