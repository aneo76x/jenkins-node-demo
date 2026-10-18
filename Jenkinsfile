pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build Artifact') {
            steps {
                sh 'tar -czf app-artifact.tar.gz app.js package.json'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'app-artifact.tar.gz', fingerprint: true
            echo 'Build successful and artifact archived!'
        }
    }
}
