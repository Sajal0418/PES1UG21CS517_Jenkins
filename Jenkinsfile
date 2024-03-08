pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                // Intentional error: Incorrect file name in the g++ command
                build 'PES1UG21CS517'
                sh 'g++ main_wrong.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
