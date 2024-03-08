pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                // Intentional error: Incorrect file name in the g++ command
                build 'PES1UG21CS517-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                eccho 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
