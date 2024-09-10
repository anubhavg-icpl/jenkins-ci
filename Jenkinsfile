pipeline {
    agent any

    tools {
        rust 'rust-stable'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'cargo build --release'
            }
        }

        stage('Test') {
            steps {
                sh 'cargo test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/release/hello_world', fingerprint: true
            }
        }
    }
}
