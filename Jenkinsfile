pipeline {
    agent {
        docker {
            image 'node-14'
        }
    }
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/wikan-dn/dev-ops-p8.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'node app.js &'
            }
        }
    }
}
