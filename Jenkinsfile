pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage...'
                sh 'python3 --version'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 test_calculator.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage...'
                sh '''
                    mkdir -p /var/lib/jenkins/deploy
                    cp calculator.py /var/lib/jenkins/deploy/
                '''
            }
        }
    }
}
