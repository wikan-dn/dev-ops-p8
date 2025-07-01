pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/wikan-dn/dev-ops-p8.git'
            }
        }

        stage('Build') {
            steps {
                bat 'npm install'
            }
        }

        stage('Test') {
            steps {
                bat 'npm test'
            }
            post {
                success {
                    echo 'Tes berhasil!'
                }
                failure {
                    echo 'Tes gagal!'
                }
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo "Menjalankan aplikasi..."'
                bat 'node app.js &'
            }
        }
    }
}
