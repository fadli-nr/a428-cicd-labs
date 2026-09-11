pipeline {
    agent {
        docker {
            image 'node:16-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                // Pasang seluruh dependensi dari package.json
                sh 'npm install'
                // Opsional: pasang cross-env & react-scripts secara manual jika hilang
                sh 'npm install --save-dev cross-env react-scripts'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}